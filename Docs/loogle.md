# Loogle for PhysLean 


## Installing the necessary programs

Updating `apt`:
```
sudo apt update
```

Installing `python3`, `python3-pip`, `nginx`, `gcc` and `git`:
```
sudo apt install python3 python3-pip nginx gcc git
```

Installing `elan`:
```
curl https://raw.githubusercontent.com/leanprover/elan/master/elan-init.sh -sSf | sh
```

Installing `prometheus-client`
```
pip3 install --break-system-packages  prometheus-client
```


## Setting environment

Setting environment variable:  
```
echo 'LOOGLE_SECCOMP=./loogle/loogle_seccomp.c' | sudo tee -a /etc/environment
source /etc/environment
```

The above can be checked with 
```
echo $LOOGLE_SECCOMP
```

## Loading in Repo


``` 
rm -r loogle;
git clone --recurse-submodules https://github.com/jstoobysmith/loogle;
cd ./loogle/;
lake update;
lake exe cache get;
lake build;
```

## Setting up nginx



Setting up the firewall:
```
ufw enable
ufw allow ssh && ufw allow http && ufw allow https
ufw status
```

Set the content of 
```
sudo nano /etc/systemd/system/myserver.service
```

To
```
[Unit]
Description=Loogle Server
After=network.target

[Service]
RemainAfterExit=True
ExecStart=/usr/bin/python3 /root/loogle/server.py
Restart=always
WorkingDirectory=/root/loogle/
User=root

[Install]
WantedBy=multi-user.target
```

This can be checked with:
```
sudo systemd-analyze verify /etc/systemd/system/myserver.service
```

Then run:
```
sudo systemctl daemon-reload;
sudo systemctl start myserver;
```

Which can be checked with 
```
sudo systemctl status myserver
```

## Updating server 


``` 
rm -r loogle;
git clone --recurse-submodules https://github.com/jstoobysmith/loogle;
cd ./loogle/;
export LIBRARY_PATH=/usr/lib/x86_64-linux-gnu:$LIBRARY_PATH
lake update;
lake exe cache get;
lake build;
```