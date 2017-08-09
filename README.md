Environment
============
* python 2.7.x
* macos sierra

Installation
============
1. You can install **seleninum** using pip.
```shell
$ pip install selenium
```
2. Install selenium [chrome webdriver](http://chromedriver.storage.googleapis.com/index.html)
3. (optional) If you want to insert crawled data into your database -we will use _**mysql**_-, also install **pymysql** using pip
```shell
$ pip install pymysql
```
4. Let's make sure it's installed. Go command line and enter
```shell
$ python
```
```python
>>> from selenium import webdriver
>>> import pymysql as mysql
>>> 
```
If no errors happen, it's installed well.

Usage
=====
1. You should open the driver.
```python
# ex) chromedriverpath = '/Users/wung/Documents/chromedriver'
driver = webdriver.Chrome(chromedriverpath) 
```
2. Then, you can open the Webpage using this code.
```python
# ex) URL = 'https://pixabay.com' or 'https://www.instagram.com'
driver.get(URL)
```
3. You can get the xpath or css selector or HTML outer using chrome developer tool.

4. And it can be used as if you use a web browser!.
	* Do you want to click button?
	```python
	# ex) button_xpath = '//*[@id='hero']/div[2]/form/table/input'
	driver.find_element_by_xpath(button's xpath).click()
	```

	* Do you want to know image's url?
	```python
	element = driver.find_element_by_xpaht(src's xpath)
	sleep(1)
	print element.get_attribute('src')
	# it will show you the image's url.
	```
	If you want to store image your own PC, try use this code.
	```python
	from urllib import urlretrieve

	# ex) fliepath_and_name = '/Users/wung/Desktop/myimg.jpg'
	urlretrieve('image url', 'file path + file name')
	```
	* Do you want to know where you are now?
	```python
	print driver.current_url
	```
	* And you can go back.
	```python
	driver.back()
	```