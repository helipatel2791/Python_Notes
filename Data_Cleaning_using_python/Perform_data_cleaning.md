* To read csv file and convert into list of lists
```
# import the reader function from the csv module
from csv import reader

opened_file = open('sample_data.csv')
read_file = reader(opened_file)
sample_data = list(read_file)

# remove the first row of the data, which
# contains the column names
sample_data = sample_data[1:]
```
* We can use str.title() method to make consistant our gender column which has "male" and "Male" as different values, also give unique name to an empty string (gender not specified)
```
for row in sample_data:
    gender = row[5]
    clened_gender = gender.title()
    if gender == "":
        gender = "Gender Unkown/Other"
    row[5] = gender
```   
* Removing brackets from the string
```
def clean_and_convert(date):
    # check that we don't have an empty string
    if date != "":
        # move the rest of the function inside
        # the if statement
        date = date.replace("(", "")
        date = date.replace(")", "")
        date = int(date)
    return date
for row in sample_data:
    Begindate = row[3]
    Enddate = row[4]
    row[3] = clean_and_convert(Begindate)
    row[4] = clean_and_convert(Enddate)
 ```
 * We should remove any special characters which makes our data inconsistent. Also, if you look at sample data, it has Some single year, e.g. 1912.
Some are ranges of years, e.g. 1913-1923. So, we can average it to one value. Below are functions created to perform these tasks
```
test_data = ["1912", "1929", "1913-1923",
             "(1951)", "1994", "1934",
             "c. 1915", "1995", "c. 1912",
             "(1988)", "2002", "1957-1959",
             "c. 1955.", "c. 1970's", 
             "C. 1990-1999"]

bad_chars = ["(",")","c","C",".","s","'", " "]

def strip_characters(string):
    for char in bad_chars:
        string = string.replace(char,"")
    return string

stripped_test_data = ['1912', '1929', '1913-1923',
                      '1951', '1994', '1934',
                      '1915', '1995', '1912',
                      '1988', '2002', '1957-1959',
                      '1955', '1970', '1990-1999']
def process_date(date):
    if "-" in date:
       date = date.split("-")
       avg = (int(date[0]) + int(date[1])) / 2
       avg = round(avg)
       return avg
    else:
       date = int(date)
       return date
processed_test_data = []
for i in stripped_test_data:
    j = process_date(i)
    processed_test_data.append(j)
```
