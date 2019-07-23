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
