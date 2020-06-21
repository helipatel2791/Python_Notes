* Python’s built-in logging module is designed to give you critical visibility into your applications with minimal setup.
* The logging module’s basicConfig() method is the easy and convenient way to configure your logger.

* Three of the main parameters of basicConfig() are:
   1. **level:** the minimum priority level of messages to log. In order of increasing severity, the available log levels are: DEBUG, INFO, WARNING, ERROR, and CRITICAL.
By default, the level is set to WARNING, meaning that Python’s logging module will filter out any DEBUG or INFO messages.
   2. **handler:** determines where to route your logs. Unless you specify otherwise, the logging library will use a StreamHandler to direct log messages to sys.stderr (usually the console).
   3. **format:** THe format you want to diplay log info, it has many attributes, main are,
      1. %(asctime)s: displays the date and time of the log, in local time
      2. %(levelname)s: the logging level of the message
      3. %(message)s: the message
 ```
 logging.basicconfig(filename='loans.log', level=logging.INFO, format='%(levelname)s:%(name)s:%(message)s')
 ```
* Now you can use logging.debug, logging.info, logging.error ... in your code wherever you want to capture logs
```
logging.info('loan approved for {} - {}'.format(fullname, email))
```
* But, if you are using logger in your main file as well as modules in your application, with basicconfig, only one logger will be used (logger of the first imported module) 
* So, if you have level=error in your module and level=debug in your main file, only level=error will be considered and it will only log error messages
* Therefore, we should always create new logger for each of module sothat we can configure it seperately. To follow the best practice of creating a new logger for each module, use the logging library’s built-in getLogger() method to dynamically set the logger name to match the name of your module:
```
logger = logging.getLogger(__name__)
```
* Now, you can set level, handlers using this specific logger like below,
```
logger.setLevel(logging.DEBUG)
formatter = logging.Formatter('%(levelname)s:%(name)s:%(message)s')
file_handler = logging.FileHandler('newlogs.log')
file_handler.setFormatter(formatter)
logger.addHandler(file_handler)
