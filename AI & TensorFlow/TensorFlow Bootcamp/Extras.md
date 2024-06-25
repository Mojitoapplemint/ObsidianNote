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