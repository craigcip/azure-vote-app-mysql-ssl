# azure-vote-app-mysql-ssl
Azure voting app (SSL mysql backend)

Orignal code: https://github.com/Azure-Samples/azure-voting-app

Modifications:
 - support SSL to MySQL (using pymysql)
 - MySQL connection vars come from environment variables
 - removed the Docker bits (as I'm installing this in a VM).
 - added Azure MySQL service CA PEM file to repo

Systemd service file:
```
[Unit]
Description=Voting App
After=multi-user.target

[Service]
EnvironmentFile=~/etc/default/votingapp
ExecStart=/usr/bin/python3 /app/main.py
Type=Idle

[Install]
WantedBy=multi-user.target
```
