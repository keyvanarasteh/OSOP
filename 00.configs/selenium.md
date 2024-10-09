Create a Selenium Python model using object-oriented programming (OOP) 
     supports multiple browsers including Chrome, Mozilla Firefox, Vivaldi, and Opera. 

This model will include methods to:
    - open URLs, 
    - run JavaScript inside the page, 
    - get content, 
    - and set content.



```python
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.chrome.service import Service as ChromeService
from selenium.webdriver.firefox.service import Service as FirefoxService
from selenium.webdriver.opera.options import Options as OperaOptions
from webdriver_manager.chrome import ChromeDriverManager
from webdriver_manager.firefox import GeckoDriverManager
from webdriver_manager.opera import OperaDriverManager

class BrowserModel:
    def __init__(self, browser_name):
        self.browser_name = browser_name.lower()
        self.driver = self._initialize_driver()

    def _initialize_driver(self):
        if self.browser_name == "chrome":
            return webdriver.Chrome(service=ChromeService(ChromeDriverManager().install()))
        elif self.browser_name == "firefox":
            return webdriver.Firefox(service=FirefoxService(GeckoDriverManager().install()))
        elif self.browser_name == "opera":
            options = OperaOptions()
            return webdriver.Opera(options=options, executable_path=OperaDriverManager().install())
        elif self.browser_name == "vivaldi":
            # Vivaldi uses the same WebDriver as Chrome
            options = webdriver.ChromeOptions()
            options.binary_location = "/path/to/vivaldi/browser"  # Update this path
            return webdriver.Chrome(service=ChromeService(ChromeDriverManager().install()), options=options)
        else:
            raise ValueError(f"Unsupported browser: {self.browser_name}")

    def open_url(self, url):
        self.driver.get(url)

    def run_js(self, script):
        return self.driver.execute_script(script)

    def get_content(self, selector, by=By.CSS_SELECTOR):
        element = WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((by, selector))
        )
        return element.text

    def set_content(self, selector, content, by=By.CSS_SELECTOR):
        element = WebDriverWait(self.driver, 10).until(
            EC.presence_of_element_located((by, selector))
        )
        self.driver.execute_script("arguments[0].innerHTML = arguments[1];", element, content)

    def close(self):
        self.driver.quit()

# Example usage:
if __name__ == "__main__":
    browser = BrowserModel("chrome")
    try:
        browser.open_url("https://www.example.com")
        print(browser.get_content("h1"))
        browser.set_content("h1", "New Heading")
        print(browser.run_js("return document.title;"))
    finally:
        browser.close()

```

This Python class `BrowserModel` provides a flexible way to interact with different browsers using Selenium. Here's a breakdown of its features:

1. It supports Chrome, Firefox, Opera, and Vivaldi browsers.
2. The `__init__` method initializes the appropriate WebDriver based on the specified browser.
3. `open_url` method navigates to a given URL.
4. `run_js` method executes JavaScript on the page.
5. `get_content` retrieves the text content of an element specified by a selector.
6. `set_content` sets the innerHTML of an element specified by a selector.
7. `close` method quits the WebDriver session.

To use this model, you'll need to install the necessary dependencies:

```
pip install selenium webdriver-manager
```

Note that for Vivaldi, you'll need to update the path to the Vivaldi browser executable in the `_initialize_driver` method.

Would you like me to explain any part of this code in more detail?