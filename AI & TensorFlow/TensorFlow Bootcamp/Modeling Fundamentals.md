# 0. Preprocessing Data
## Normalization
Change the values of *numerical columns in the dataset to a common scale*, \[0,1\], without distorting the distribution
- `sklearn.MinMaxScaler()`
- Use as **default scaler** with neural networks

## Standardization
Removes the mean and divides each value by the [[3. Spread and Variance#Standard Deviation|standard deviation]]; transform a feature to have close to [[5. Normal Distribution|normal distribution]]
- `sklearn.StandardScaler()`
- This **reduces the effect of outliers**

## Using `sklearn` for Preprocessing
When we are using the column transformer, we need to *fit the transformer* to the `training_data`, then use it to transform the `test_data`

```python
from sklearn.compose import make_column_transformer
from sklearn.preprocessing import MinMaxScalar, OneHotEncoder

# Create a column transformer
ct.make_column_transformer((MinMaxScaler(), ['list of columns']),
						(OneHotEncoder(handdle_unknown="ignore")), ['list of columns'])

# Fit the column transformer to training data
ct.fit(X_train)

# Transform training and test data with normalization and OneHotEncoder
X_train_normal = ct.transform(X_train)
X_test_normal = ct.transform(X_test)
```

## Splitting Models into Train/Test Sets
The total data set is divided into three sets
- *To test the ability for a ML model to perform well on data it hasn't seen before*

Training Set (Course Materials)
- The model **learns** from this data
- *70-80%* of the total data available
- Features: `X_train` / Labels: `y_train`
Validation Set (Practice Exam)
- The model gets **tuned** on this data
- *10-15%* of the data available
Test Set (Final Exam)
- The model gets **evaluated** on this data to test what is has learned
- *10-15%* of the total data available
- Features: `X_test` / Labels: `y_test`

`train_test_split('features', 'labels', test_size, random_state)`
- `test_size`: Between 0 to 1; represent the proportion of the test split
- `random_state`: Work as `random_seed`
```python
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split()
```

# 1. Creating a Model
Define the input, output and hidden layers
- `tf.keras.layers.Dense('number of neurons')`
- Use **`tf.float32` as default**
- Name the layer with `name` parameter

```python
# Set random seed
tf.random.set_seed(42)

# Optionally, the first layer can recieve an 'input_shape' argument
model=tf.keras.Sequential()
model.add(tf.keras.layers.Dense(8,input_shape=(16)))

# Afterwards, we do automatic shape inference
 nmodel.add(tf.keras.layers.Dense(100))

# Instead of using tf.add() method, we can put layers as a list
mode = tf.keras.Sequential([tf.keras.layers.Dense(8), tf.keras...])

```

# 2. Compiling a model
Define 
- A loss function 
- Optimizer: Tells our model how to imporve the patterns its learning 
	- `Learning Rate(learning_rate)`: How much the model should improve at each step(higher `lr`, the optimizer pushes the model more)
- Evaluation metrics: What we can use to interpret the performance of our model
```python
model.compile(loss=tf.keras.losses.mae,
			 optimizer=tf.keras.optimizers.SGD(),
			 metrics=["mae"])
# or
model.compile(loss=tf.keras.losses.mae,
			 optimizer=tf.keras.optimizers.Adam(learning_rate=0.0001),
			 metrics=["mae"])

# We can specify parameters using String by ""
 => optimizer="sgd"
```

# 3. Fitting the model
Letting the model try to find pattern
```python
model.fit('features', 'labels', epochs='int') 
```
- `Epochs` refers to the number of opportunity for the model to find pattern
- The `features` is required to be rank of higher than 1, thus, if the `features` is a vector, we need to [[AI & TensorFlow/TensorFlow Bootcamp/1. TF Fundamentals#Using `tf.expand_dims`|expand it]]

# 4. Evaluating the Model
 **Note:** When validation loss starts to increase, its likely that it's overfitting the training data that its ability to generalize to unseen data is diminished
- [[AI & TensorFlow/TensorFlow Bootcamp/2. Neural Network Regression with TF#Evaluating Model's Predictions with Regression Evaluation Metrics|Regression Evaluation]]
- [[AI & TensorFlow/TensorFlow Bootcamp/3. Neural Network Classification in TF#Classification Evaluation Method|Classification Evaluation]]

# 5. Improve Model
We can improve the model by altering the previous steps

1. Creating the model
	- Add more layers
	- Increase number of hidden units(neurons)
	- Change activation function
2. Compiling a model
	- Change optimization function
	- **Change the learning rate of the optimization**
3. Fitting a model
	- More epoch
	- Fitting on more data

**Note)**
- Not all of them lead to improve the model
- Metrics sometimes can't be a good representative of how good the model is
- *Start with the small experiments* and make sure they work and then increase their scale when necessary

## Finding an Ideal Learning Rate
Specifying the learning rate dictates the model to improve for certain amount for each epoch
- Default learning rate usually works, so **try default first and modify it**
- Ideal Learning Rate will let the model to improve faster(Require less epochs)

Learning Rate [[5. Transfer Learning with TF#Callbacks|Callback]]
```python
# traverse a set of learning rate values starting from 1e-4, increasing by 10**(epoch/20) every epoch 
lr_scheduler = tf.keras.callbacks.LearningRateScheduler(lambda epoch: 1e-4 * 10**(epoch/20))

# Fit the model (passing the lr_scheduler callback) 
history = model_9.fit(X_train, y_train, epochs=100, callbacks=[lr_scheduler])

# Plot loss vs. lr
lrs = 1e-4 * 10**(tf.range(100)/20)
plt.semilogx(lrs, history.history["loss"]) # we want the x-axis (learning rate) to be log scale 
plt.xlabel("Learning Rate") 
plt.ylabel("Loss") 
plt.title("Learning rate vs. loss")
plt.show()
```
![[Pasted image 20240524170233.png|400]]

Rule of Thumb
- Where the loss is *still decreasing but not quite flattened out*
- Usually about *10x smaller than the bottom* of the curve

