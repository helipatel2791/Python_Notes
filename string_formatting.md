   ### formatting with placeholders:

    ```
    I/P: print("I'm going to inject %s text here and %s text here" %('some','more'))
    O/P: I'm going to inject some text here and more text here
    ```
    
   * %s converts to string, %d converts number to integer (without rounding)
 
   ```
   print('I wrote %s pages today', %3.75) --> replaces %s to 3.75
   print('I wrote %d pages today', %3.75) --> replaces %d to 3
   ```
   
  ```
  I/P: print('Floating point numbers: %5.2f', %(13.144))
  O/P: Floating point numbers: 13.14
  ```
  * 5.2f means 5 --> minimum number of characters string should contain, 2 --> number to show past the decimal point
  
 ### .format method:
 
 ```
 I/P: print('I love {} and "{}!"'.format('dancing', 'coding'))
 O/P: I love dancing and coding
 ```
 * {} takes objects given in .format in order
 ```
 I/P: print('{1} and {0}'.format('Python', 'SQL')) 
 O/P: SQL and Python
 ```
 * We can also specify position of objects as {1}, {0} etc.
 
  ```
  I/P: print('{0:11} | {1:9}'.fomat('Vegetable', 'Quantity'))
       print('{0:11} | {1:9}'.fomat('Cucumber', 5))
	   
  O/P: Vegetable  | Quantity
       Cucumber   |        5
 ```
 * Here, 0 indicates Cucumber, 1 indicates 5 and so on..11 and 9 are widths assigned
 ### f-strings:
 * Introduced in Python 3.6
 ```
 I/P: name = 'Heli'
      print(f"Hello! My name is {name}")
 O/P: Hello! My name is Heli
 ```
 * We can use objects directly in the string using f-string
