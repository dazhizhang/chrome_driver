# chrome_driver


# 等待的种类
	public static boolean wait(WebDriver driver, Indicator indicator, By by, WaitTime waitTime) {
		try {
			switch (indicator) {
			case Present:
				return (new WebDriverWait(driver, waitTime.val())).until(ExpectedConditions.presenceOfElementLocated(by)) != null;
			case Visible:
				return (new WebDriverWait(driver, waitTime.val())).until(ExpectedConditions.visibilityOfElementLocated(by)) != null;
			case Invisible:
				return (new WebDriverWait(driver, waitTime.val())).until(ExpectedConditions.invisibilityOfElementLocated(by));
			case Clickable:
				return (new WebDriverWait(driver, waitTime.val())).until(ExpectedConditions.elementToBeClickable(by)) != null;
			}
			
			throw new IllegalArgumentException("Unsupported Indicator: " + indicator);
		} catch (WebDriverException e) {
			return false;
		}
	}

# 访问网页
driver.get(url);


# 填写input文本框
PageUtils.setValue(driver, driver.findElement(By.name("email_address")), buyer.getEmail());

PageUtils.setValue(driver, driver.findElement(By.id("email_address")), buyer.getEmail());

PageUtils.click(driver, By.cssSelector("div#buttons > a.amzn-btn.btn-prim-med"));

# 在同类元素中查找某个特定值
		List<WebElement> checkboxes = driver.findElements(By.cssSelector("input[type=checkbox]"));
		if (checkboxes != null && checkboxes.size() > 1) {
			for (WebElement we : checkboxes) {
				we.click();
			}
			logger.debug("当前订单有2种以上产品，已分别勾选");
		}
<br>
根据某种特定类型的特定id两个参数找元素
<br>
submitElements = driver.findElements(By.xpath("//span[@id='acrPopover']"));
<br>
<br>
找元素特定属性
title = submitElements.getAttribute("title");
<br>
用class名字找元素
<br>
driver.findElements(By.className("a-row"));
<br>

# botton 点击失效
WebElement we

we.sendKeys(Keys.RETURN);   
or
we.sendKeys(Keys.ENTER);

# 得到页面元素内容
 for (WebElement bt : buttonList) {
                        System.out.println(bt.getAttribute("outerHTML"));
                    }


# selenium
使用selenium附加已经打开的Chrome浏览器
<br>
https://www.zhupite.com/python/python-selenium-debug-existing-browser.html
<br>
步骤<br>
关闭所有Chrome浏览器，并用命令行方式启动：<br>
"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe<br>
" --remote-debugging-port=8888<br>
实际上是开放了一个调试端口，这个端口可以自行修改。<br>
