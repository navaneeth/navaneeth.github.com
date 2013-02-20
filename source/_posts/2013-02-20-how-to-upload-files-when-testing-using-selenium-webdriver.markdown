---
layout: post
title: "How to upload files when testing using Selenium Webdriver"
date: 2013-02-20 15:42
comments: true
categories: java, webdriver, selenium, testing, automated-testing
---
You can use the following code to set a file path to the file upload control. 

```java
WebElement file = driver.findElement(By.id("control_id"));
file.sendKeys("/full/path/to/file");
```

You need to pass full path to the `sendKeys()` for it to work. Otherwise `sendKeys()` fails silently. 
