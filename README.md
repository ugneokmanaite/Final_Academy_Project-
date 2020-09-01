# Project Summary :thought_balloon:

- [x] Clone Python App from Github
- [x] Run the app & Test the app in pycharm virtual environment
- [x] Continuous Integration (CI) with Jenkins 
- [x] Continuous Delivery and Deployment on EC2
- [x] Deployment with ECS on AWS
- [x] Presentation & Demo Video 

** DOD = to get app running on EC2 with full functionality as per the following readme [click here]()

![image]()

# Testing Python App :snake:

## Step 1: Prerequisites

- [x] Pycharm IDE
- [x] Python 3.7 /3.8 installed

## Step 2: Clone repo 
Clone the repo and save folders with the required code 

## Step 3: Install plugins/packages 
- Should automatically be picked up by Pycharm when opening the following file : 
```
main.py
```

## Step 4: Set environment
- Open `config.ini` file and set test environment to `live`
- Click on terminal and run `python -m pytest tests/`

## Step 5: If tests are stil failing check the following things:

### Error when attempting to run pytest
![image]()

- try to update `pluggy dependency`
- run the following command in terminal
```
pip install -U pluggy

OR

pip3 install -U pluggy
```
- This should solve the issue and tests should now run!

### Test Error 1: Extra row being created when creating csv file 
 [image]()
 - need to add `newline=''` (empty string) parameter
 - https://stackoverflow.com/questions/3348460/csv-file-written-with-python-has-blank-lines-between-each-row

 - It should now look like this 
 ![image]()

### Test Error 2: Inconsistent naming convention in files
![image]()

- Open `test_html_object_manager.py`
- Ensure to change 
```
HtmlObjectManager 

TO 

HttpManager
````
- This has to be done throughout the whole file!
- It should now look like this [image]()

### Test Error 3: def test_html_manager_returns_html_from_url

![image]()

- Open `test_html_object_manager.py`
- Go to line 26 and 27 

![image]()
```
    def test_html_manager_returns_html_from_url(self, html_manager_object):
        assert 'Tracking the IT job market' in html_manager_object.html
```
- Ensure 'Job Market' is capitilized as this is the way it is in site html

- It should now look like this 
![image]()


## All tests should now pass!!

![image]()

