
### Working with the datetime module

* To import datetime module
```
import datetime as dt
```

* Creating datetime.datetime object given a month, year, and day:
```
my_birthday = dt.datetime(1992, 7, 2)
```

* Creating a datetime.datetime object from a string:
```
your_birthday = dt.datetime.strptime("24/12/1984", "%d/%m/%Y")
```

* Converting a datetime.datetime object to a string:
```
dt_object = dt.datetime(1984, 12, 24)
dt_string = dt_object.strftime("%d/%m/%Y")
```

* Instantiating a datetime.time object:
```
new_time = datetime.time(hour=0, minute=0, second=0, microsecond=0)
```

* Retrieving a part of a date stored in the datetime.datetime object:
```
my_birthday.year
```

* Creating a datetime.time object from a datetime.datetime object:
```
d2_dt = dt.datetime(1946, 9, 10)
d2 = d2_dt.time()
```

* Creating a datetime.time object from a string:
```
d3_str = "17 February 1963"
d3_dt = dt.datetime.strptime(d3_str, "%d %B %Y")
d3 = d3_dt.time()
```

* Instantiating a datetime.timedelta object:
```
d4 = dt.timedelta(weeks=3)
```

* Adding a time period to a datetime.datetime object:
```
d1 = dt.date(1963, 2, 26)
d1_plus_1wk = d1 + dt.timedelta(weeks=1)
```
