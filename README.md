# 🚨 burp-api-failure-monitor
A Burp Suite extension to capture API failure responses (4xx/5xx) during application flows and send real-time alerts to Slack.

# 📌 Overview
```burp-api-failure-monitor``` is a lightweight **Burp Suite extension** built to automatically capture **backend API failures while executing mobile or web application flows**.

Whenever an API returns a failure response (4xx or 5xx), the extension:

- Logs the response to a .txt file
- Sends the error details to a configured Slack channel

This enables **faster debugging, better visibility, and real-time alerts** during test execution.

# 🎯 Key Features

- Captures API failure responses automatically
- Supports HTTP status codes 400–599
- Logs failed responses to a text file
- Sends alerts to Slack for instant visibility
- Works seamlessly with mobile apps via emulator/device proxying
- Ideal for exploratory testing and automation-assisted monitoring

# 🔧 Prerequisites

- Burp Suite installed
- Jython configured in Burp (for Python extensions)
- Android emulator or physical device
- Slack Incoming Webhook URL

# 🚀 Setup & Usage
1️⃣ Install the Burp Extension
- Open Burp Suite → Extensions
- Add errorResponseExtension.py as a Python (Jython) extension
- Ensure the extension loads successfully without errors

2️⃣ Configure Proxy
- Configure the Android emulator or device to route traffic through Burp Proxy
- Confirm API calls are visible under Proxy → HTTP history

3️⃣ Execute Application Flow
- Launch the application
- Perform any user flow that triggers API requests

4️⃣ API Failure Detection Logic >> Any API response with the following status codes is treated as a failure:  
- ```400 <= status_code <= 599```

5️⃣ Logging & Slack Notification >> The failed API response is:
- Stored in a .txt file
- Automatically sent to the configured Slack channel

# 💡 Optional Enhancement
This extension can be used alongside **Appium automation** to capture backend API failures during **automated mobile test execution**.


# 🎥 Demo (Execution Flow)

A demo video showcasing the extension execution is available.
All API endpoints and response payloads are masked to ensure security and confidentiality.

https://github.com/user-attachments/assets/ce46aa6a-ab93-45d9-aaf7-19c145c53133



Below is the screenshot of Failed response sent to Slack channel

<img width="3010" height="1748" alt="failedResponse_sent_to_slack" src="https://github.com/user-attachments/assets/4e40781b-1626-47ce-b0af-02fb841af42b" />


