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

Model Checkpointing
- Save model as it trains 
- Enable to stop while it's training and comeback later

Early Stopping
- Enable to stop earlier if the model stops improving