# Honeypotpy



🕵️ Web Honeypot (WordPress Fake Login)

This project is a deceptive honeypot that simulates a WordPress admin login page (/wp-admin).
It is designed to log attacker behavior (e.g., usernames, passwords, IP addresses) when they attempt to break in.

Features

Fake WordPress-style login page (wp-admin.html)

Built with Flask 

Logs:

Attacker IP address

Username and Password attempts

Commands and their work

Logging with RotatingFileHandler → prevents logs from growing infinitely

Configurable username & password (default: admin / password)

Runs on any port (default: 5000)

Installation

Clone the repo / copy project

cd web-honeypot


Create a virtual environment

python3 -m venv venv
venv\Scripts\activate      # Windows PowerShell


Install dependencies

flask
dash==2.17.1 
dash_bootstrap_components==1.6.0
dash_bootstrap_templates==1.2.3 
flask==3.0.3 pandas==2.2.2
paramiko==3.4.0
plotly==5.23.0 
python-dotenv==1.0.1 
requests==2.32.3



Start the honeypot

python web_honeypot.py


Access the honeypot in browser

http://localhost:5000/


(replace localhost with your server IP if deployed remotely)

Login Page Preview
The page looks like a WordPress login page.
Any login attempt will be logged.

📂 Project Structure
honey/
│── web_honeypot.py      # Main honeypot logic (Flask app + logger)
│── templates/
│   └── wp-admin.html    # Fake WordPress login page
│── http_audits.log      # Log file storing attacker activity
│── README.md            # Documentation



2025-08-30 12:15:23 Client with IP address: 192.168.1.10 entered
 Username: admin, Password: 123456


Logs are rotated when file size exceeds 2KB (configurable in code).

🛡️ Warning

This honeypot is only for educational & research purposes.

Do not deploy on production servers without proper isolation.

Logs may contain sensitive attacker data, handle with care.

🚀 Future Improvements

Add geolocation lookup for attacker IPs

Store logs in a database 

Realistic redirection to WordPress dashboard clone

Integrate with alert system (email / Telegram bot when attacker logs in)
