###### A decorator is just a function that takes another function as an argument, adds some kind of functionality and return another function

```
def decorator_function(original_function):
    def wrapper_function()
	                       ---->Add our extra functionality here
        return original_function
    return wrapper_function
```

```
@decorator_function	
def display():
    print('This is a display func')
```
	
* Now, @decorator_function above will take display() function as an argument and return its execution and also execute our wrapper function which has some extra functionality to be added to our original function.

* @decorator_function is same as decorated_display = decorator_function(display)
                                decorated_display()
