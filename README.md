import time
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys

# Set the path to the ChromeDriver executable
chrome_driver_path = r"C:\zz\chrome\chromedriver.exe"

# Create ChromeOptions instance and set executable path
chrome_options = webdriver.ChromeOptions()
chrome_options.add_argument(f"executable_path={chrome_driver_path}")

# Create Chrome WebDriver instance with ChromeOptions
driver = webdriver.Chrome(options=chrome_options)

# Open the specified URL
driver.get("https://usstagingms.hpdaas.com/")
driver.maximize_window()

# Wait for the page to load (you may increase this time if needed)
time.sleep(15)

#accp/rejct
accpt_xpath = '/html/body/div[2]/div[2]/div/div/div[2]/div/div/button[2]'
accpt = driver.find_element(By.XPATH, accpt_xpath)
accpt.click()

time.sleep(3)

# hpid
element_xpath = '//html/body/div[1]/div/div/div[2]/div/div/div[2]/button[2]'
element = driver.find_element(By.XPATH, element_xpath)
element.click()
time.sleep(5)

# loginid
input_xpath = '/html/body/div[2]/div/div/div[2]/div/div/form/div[1]/div[1]/div/input'
input_element = driver.find_element(By.XPATH, input_xpath)
input_element.send_keys("sandwalkerstaging@yopmail.com")

# Click the login button
button_xpath = '/html/body/div[2]/div/div/div[2]/div/div/form/div[2]/button'
button_element = driver.find_element(By.XPATH, button_xpath)
button_element.click()
time.sleep(4)

# Wait for the password field and enter the password
pass_input_xpath = '/html/body/div[2]/div/div/div[2]/div/div/div/form/div[1]/div/div/div/input'
pass_input_element = driver.find_element(By.XPATH, pass_input_xpath)
pass_input_element.send_keys("Security@123")

#signin
sign_xpath = '/html/body/div[2]/div/div/div[2]/div/div/div/form/div[2]/button'
sign = driver.find_element(By.XPATH, sign_xpath)
sign.click()
time.sleep(30)

# Perform additional actions if needed

# Close the browser window
driver.quit()

