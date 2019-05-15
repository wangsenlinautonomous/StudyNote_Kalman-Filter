# StudyNote_Kalman-Filter

## 1D Kalma Filter
Measurement:

<img src="https://user-images.githubusercontent.com/40875720/57757802-dbb54d00-7728-11e9-9667-9156f84d1b7a.png" width="600">

Predict:

<img src="https://user-images.githubusercontent.com/40875720/57757963-2fc03180-7729-11e9-8182-d231c82a0859.png" width="600">

```

# the update function
def update(mean1, var1, mean2, var2):
    ''' This function takes in two means and two squared variance terms,
        and returns updated gaussian parameters.'''
    # Calculate the new parameters
    new_mean = (var2*mean1 + var1*mean2)/(var2+var1)
    new_var = 1/(1/var2 + 1/var1)
    
    return [new_mean, new_var]


# the motion update/predict function
def predict(mean1, var1, mean2, var2):
    ''' This function takes in two means and two squared variance terms,
        and returns updated gaussian parameters, after motion.'''
    # Calculate the new parameters
    new_mean = mean1 + mean2
    new_var = var1 + var2
    
    return [new_mean, new_var]
```
