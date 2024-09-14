from flask import Flask, request
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

app = Flask(__name__)

@app.route('/login', methods=['POST'])
def login():
    username = request.form.get('username')
    password = request.form.get('password')
    
    driver = webdriver.Chrome(executable_path="/path/to/chromedriver")
    driver.get("https://www.redbubble.com")

    # Perform Redbubble login using Selenium
    login_button = driver.find_element(By.LINK_TEXT, "Login")
    login_button.click()

    username_input = driver.find_element(By.ID, "username")
    username_input.send_keys(username)

    password_input = driver.find_element(By.ID, "password")
    password_input.send_keys(password)
    password_input.send_keys(Keys.RETURN)

    time.sleep(5)
    driver.quit()
    return "Login successful!"

if __name__ == '__main__':
    app.run(debug=True)
