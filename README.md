# ไพที กรุ้ป CCTV Center

## Title: AI-Powered CCTV Alerting Workflow
An infographic showing how a VMS, n8n, and a Django web app work together to create an automated incident response system.

* 1. DETECTION: The Incident
[Icon: Security camera with a motion symbol]

What: The main VMS (Video Management System) detects a predefined event, such as motion in a restricted area after hours.

Action: It instantly sends the event data (camera ID, timestamp, event type) to a secure n8n webhook URL.

* 2. AI & RULES: The Brain (n8n)
[Icon: n8n logo or a brain with gears]

What: An n8n workflow receives the data and acts as the intelligent rule engine.

Action: It processes your custom logic. For example: IF event is 'motion' AND time is after '10 PM' AND location is 'Warehouse' THEN trigger alerts.

* 3. CONTROL & LOGGING: The Hub (Django 5+)
[Icon: Django logo or a web browser]

What: The secure, full-stack Django web application serves as the operator's main control center.

Action: It receives an API call from n8n to log the incident in its database and prepares to alert the live operator.

* 4. NOTIFICATION: The Actions (Run in Parallel)
[Icon: A branching arrow pointing to three distinct icons]

What: Once the rules are met, n8n and Django execute three alerts simultaneously.

## Actions:

* A) Instant On-Screen Alert:

[Icon: A monitor with an exclamation mark]

Django uses WebSockets to push a real-time notification, instantly bringing the relevant camera to a "Focus Display" on the operator's screen.

* B) Email Alert:

[Icon: An email envelope]

n8n automatically composes and sends a detailed incident report email to a predefined security distribution list.

* C) LINE Mobile Alert:

[Icon: The LINE app logo]

n8n calls the LINE Notify API to send an immediate, direct message to a specific person or group chat for on-the-go awareness.