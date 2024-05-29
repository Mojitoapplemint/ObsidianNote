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
 
