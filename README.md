# Py-Easy-Scrap

## Description

A useful package for web scraping with Selenium

## Installation

```bash
pip install py-easy-scrap
```

## Requirements

- Python 3.7 or higher
- Selenium, along with __GeckoDriver__ (Firefox)

## Usage

In your project directory, create a new directory for your logs - it can be just called 'logs':
```bash
mkdir logs
```

Then, import the package:
```python
import pyeasyscrap as pes
```

### Get WebDriver

```python
driver = pes.get_webdriver(headless)
```
This will return an instance of webdriver.Firefox (GeckoDriver).

### Get Element

```python
element = pes.get_element(driver, value="element_xpath")
```

This will return the web element found using the specified driver and value. By default, this function uses 'XPATH' as the method of searching. However, you can change this by providing 'ID' or 'LINK_TEXT' as the 'by' argument.

Please be aware that the method of searching ('XPATH', 'ID', or 'LINK_TEXT') highly depends on the webpage structure. Therefore, it is essential to inspect the webpage beforehand.

Also, please remember to replace `"element_xpath"` with the actual Xpath, ID, or link text of the element you want to find.


### Scroll to Element

```python
pes.scroll_to(driver, element)
```

This will use JavaScript to scroll the view of the given webdriver to the specified web element.

### Ask for Data

```python
required_data = ("username", "password")
file_name_no_extension = "user_credentials"
pes.ask_for_data(required_data, file_name_no_extension)
```

This will return a dictionary containing the collected data and will create a JSON configuration (.conf) file.

### Check File

```python
pes.check_file("path_to_file")
```

This will return either True or False based on file existence

Please note that the above code snippets are basic examples of how to use those functions. Depending on the exact specifications of your use case, additional setup may be necessary (e.g. logging into a website before trying to scroll to an element).

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

MIT

