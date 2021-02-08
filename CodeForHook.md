---
layout: default
title: "Code for Hook"
tags: sauce,sauces,stuff
---
# Code for Captain Hook

### waitForDocumentCheckCompletion
### This checks and waits for the html to return that it has fully loaded...
### If you remove all the GAI fluff, you could just do the simple one below.  That will wait up to 
### 30 seconds for the page to load...
```java
void waitForLoad(WebDriver driver) {
    new WebDriverWait(driver, 30).until((ExpectedCondition<Boolean>) wd ->
            ((JavascriptExecutor) wd).executeScript("return document.readyState").equals("complete"));
}
```

### But with the GAI fluff:

```java
private void waitForDocumentCheckCompletion(WebDriver driver, DriverManager driverManager) {
		if (ThreadContext.get("DOCUMENT_CHECK").toLowerCase().equals("true")) {
			long startTime = System.currentTimeMillis();
			//Check for ready state of html document...
			_log.info("Waiting for document to return ready state = complete for up to " + ThreadContext.get("readyStateTimeout") + " seconds...");
			new WebDriverWait(driver, Integer.parseInt(ThreadContext.get("readyStateTimeout"))).until((Function<WebDriver,
					Boolean>) input -> {
				Boolean documentReady;
				try {
					documentReady = (input != null) && ((JavascriptExecutor) input)
							.executeScript("return document.readyState").equals("complete");
				} catch (UnhandledAlertException uae) {
					String dialogChoice = ConfigurationManager.getValueOrDefault(Constants.RETRY_DIALOG_ACTION, "ACCEPT");
					if ("ACCEPT".equals(dialogChoice) || "DISMISS".equals(dialogChoice)) {
						_log.warn(dialogChoice + "ing the unhandled alert found, then moving on...");
						TestStepAction accept = getAction(AlertAction.NAME);
						accept.execute(driverManager, new TestStep("unhandledAccept", "", AlertAction.NAME, dialogChoice));
					}
					documentReady = true;
				} catch (Exception e) {
					_log.info("Unable to check document state due to exception:  " + e);
					documentReady = true;
				}
				return documentReady;
			});
			long duration = ((System.currentTimeMillis() - startTime));
			_log.info("Document Ready state check completed in " + duration + " milliseconds, moving on...");
		} else {
			_log.info("Skipping document check this time around...");
		}
	}
```


### waitForAjaxCheckCompletion
### This waits for any ajax/javascript to complete before moving on...
### If you remove all the GAI fluff, you get:
```java
public boolean waitForJSandJQueryToLoad() {

    WebDriverWait wait = new WebDriverWait(driver, 30);

    // wait for jQuery to load
    ExpectedCondition<Boolean> jQueryLoad = new ExpectedCondition<Boolean>() {
      @Override
      public Boolean apply(WebDriver driver) {
        try {
          return ((Long)((JavascriptExecutor)getDriver()).executeScript("return jQuery.active") == 0);
        }
        catch (Exception e) {
          // no jQuery present
          return true;
        }
      }
    };
```

### But with the GAI fluff:

```java
	private void waitForAjaxCheckCompletion(WebDriver driver) {
		if (ThreadContext.get("SYNC_AJAX").toLowerCase().equals("true")) {
			_log.info("Running ajax checks for " + ThreadContext.get("SCREEN_OBJECTIVE") + "...");
			long startTime = System.currentTimeMillis();
			_log.info("Waiting for ajax calls to return " + ThreadContext.get("expectedAjaxThreads") + " active threads for up to " + ThreadContext.get("SYNC_AJAX_TIMEOUT") + " seconds...");
			new WebDriverWait(driver, Integer.parseInt(ThreadContext.get("SYNC_AJAX_TIMEOUT"))).until((Function
					<WebDriver, Boolean>) input -> {
				Boolean ajaxReady;
				try {
					ajaxReady = (input != null) && (Boolean) (((JavascriptExecutor) input)
							.executeScript("return jQuery.active == " + ThreadContext.get("expectedAjaxThreads")));
				} catch (Exception e) {
					_log.info("No Ajax running on the page...");
					ajaxReady = true;
				}
				return ajaxReady;
			});
			long duration = ((System.currentTimeMillis() - startTime));
			_log.info("Ajax checks completed in " + duration + " milliseconds, moving on...");
		}
		else {
			_log.info("Skipping ajax checks...");
		}
	}
```


