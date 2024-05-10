# Removing all CUDA messages 
```python
import os
os.environ['TF_CPP_MIN_LOG_LEVEL'] = '1' # from [0,1,2,3]
```