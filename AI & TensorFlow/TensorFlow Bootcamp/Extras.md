# Removing all CUDA messages 
```python
import os
os.environ['TF_CPP_MIN_LOG_LEVEL'] = '1' # from [0,1,2,3]
```

# Checking Accessibility of GPU
```python
print(tf.config.list_physical_devices("GPU"))
```

# Read Dataset from GitHub
1. Click `Raw` at GitHub
![[Pasted image 20240514060648.png|300]]
2. Copy the link
3. Read it with `pandas` library
	- `pd.read_csv('link')`

# Plotting Loss & Evaluation Curves
```python
# Suppose that model is using "accuracy" evaluation
history = model.fit(...)

history_df = pd.DataFrame(history.history)

loss = history_df['loss']
val_loss = history_df['val_loss']

accuracy = history_df['accuracy']
val_accuracy = history_df['val_accuracy']

epochs = range(len(history_df['loss']))

plt.plot(epochs, accuracy, label = 'accuracy')
plt.plot(epochs, val_accuracy, label = 'val_accuracy')
plt.title("accuracy vs epoch")
plt.legend()

plt.figure()
plt.plot(epochs, loss, label = 'loss')
plt.plot(epochs, val_loss, label = 'val_loss')
plt.title("loss vs epoch")
plt.legend()
plt.show()
```
 
# Comparing the results of different models
Compare with `pandas` DataFrame
```python
import pandas as pd

model_results = [["model_1", mae_1.numpy(), mse_1.numpy()], 
				 ["model_2", mae_2.numpy(), mse_2.numpy()], 
				 ["model_3", mae_3.numpy(), mse_3.numpy()]] 

all_results = pd.DataFrame(model_results, columns=["model", "mae", "mse"]) all_results
```

**Note:**
- Tracking the result of experiment is important in ML modeling
- Following can be helpful
	- TensorBoard
	- Weights & Biases

**Note:**
The same model with even *slightly* different data can produce *dramatically* different results. Thus, it is important to compare different model on the same criteria
- Same architecture but different data
- Same data but different architecture

# Plotting Model
```python
from tf.keras.utils import plot_model

# Create a diagram of Neural Network
plot_model(model='model', show_shape=True)

```

# Saving & Loading Model
We can use our model outside of TF

`model.save("filpath/filename")`
- `SavedModel` format by default
- `HDF5` format by adding `.h5` after the file name
- Compatible with TF Server

`tf.keras.models.load_model("filpath/filename")`
- It still stores the pattern that the model already learned in both format

# Make a Prediction from Model
To visualize the prediction, it is a good idea to plot them against the ground truth labels
- `y_test / y_true` versus `y_pred` 
```python
y_pred=model.predict(X_test)
```

# Checking Current Status
`tf.summary()`
- `Total Param`: Total number of parameters in the model
- `Trainable Params`: Parameter that the model can update as it trains
- `Non-Trainable Params`: Parameter that won't be updated; when trained model participates during transfer learning

[Additional Video{MIT Introduction to Deep Learning)](https://www.youtube.com/watch?v=ErnWZxJovaM)

# Callbacks
- Extra functionality that can be added to model *while* its training, evaluation or inference
- `tf.keras.callbacks`

## TensorBoard
Log the performance of multiple models and then *view&compare them in a visual way*
```python
# Create tensorboard callback (functionized because need to create a new one for each model) 
import datetime 
def create_tensorboard_callback(dir_name, experiment_name): 
	log_dir = dir_name + "/" + experiment_name + "/" + datetime.datetime.now().strftime("%Y%m%d-%H%M%S") 
	tensorboard_callback = tf.keras.callbacks.TensorBoard( log_dir=log_dir ) 
	print(f"Saving TensorBoard log files to: {log_dir}") 
	return tensorboard_callback
```

**Steps**
1. Pass the tensorboard callback while fitting
2. Type `tensorboard --logdir "File_Path"`
3. Go to `http://localhost:6006`

## Model Checkpoint
Save model as it trains (the full model or just the weights)
- Enable to stop while it's training and comeback later
```python
tf.keras.callbacks.ModelCheckpoint(filepath="file_path",
								  save_weights_only=,)
								  save_best_only=,
								  save_freq="epoch", # save every epoch
								  verbose=1

# Saved weight can be loaded as follows:
same_model.load_weights("file_path")
```

Early Stopping
- Enable to stop earlier if the model stops improving


# `classification_report()`
`classification_report()` function in `sklearn.metrics` provides [[AI & TensorFlow/TensorFlow Bootcamp/3. Neural Network Classification in TF#Classification Evaluation Method|precision, recall and f1]] score per class
```python
from sklearn.metrics import classification_report()

print(classification_report(y_true, y_preds))
```

# TensorFlow Dataset: `tf.data.DataSets`
[API]([TensorFlow Datasets](https://www.tensorflow.org/datasets/overview))
A place for prepared and ready to use machine laerning datastes
- Data is already in **tensor format**
- Well established: suit for practice
- For experiment with different modelling techniques on a consisitent dataset
- **Static**, do not change like real world datasets

## Loading Data
```python
import tensorflow_datasets as tfds

(train_data, test_data), ds_info = tfds.load(name = "name",
											 split = ["train", "validation", (or) "test"],
											 shuffle_files=True,
											 as_supervised=True,
											 with_info=True)

```
we can use `ds_info` to get information about dataset(e.g. class_names)
- Require `with_info=True` parameter
## Taking Sample
```python
sample = train_data.take('number_of_sample')
```

## Preprocessing Data
Dataset might not be in form that Neural Network prefers, thus preprocessing is often required
- Data in `float32` dtype
- Making all tensors be same shape, size
- Scaled/Normalized

# Mixed Precision
Use of both 16-bits and 32-bits floating point types in a model during training to make it run faster and use less memory
- Require GPU computing capability 7+

```python
from keras import 
```