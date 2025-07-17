

# Dashboard 

This operates in the same way as loogle. 

In 
```
sudo nano /etc/systemd/system/dashboard.service
```

put 
```
[Unit]
Description=Dashboard Server
After=network.target

[Service]
RemainAfterExit=True
ExecStart=/usr/bin/python3 /root/dashboard.py
Restart=always
WorkingDirectory=/root/       
User=root

[Install]
WantedBy=multi-user.target
```

```
sudo systemctl enable dashboard.service
sudo systemctl start dashboard
sudo systemctl status dashboard
```

```
sudo ufw allow 8097
```