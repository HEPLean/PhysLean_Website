# Loogle for PhysLean 

To access server remotely use
```
ssh root@159.65.55.208
``` 
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

may also need to run 
```
apt install elan
```

Installing `prometheus-client`
```
pip3 install --break-system-packages  prometheus-client
```

I having problems with secomp
```
sudo apt-get install libseccomp-dev
```
or 
```
sudo apt install --reinstall libseccomp-dev
export LIBRARY_PATH=/usr/lib/x86_64-linux-gnu:$LIBRARY_PATH
lake build
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

If want to build in background can use: 
``` 
touch /root/loogleOut.txt 
nohup lake build > /root/loogleOut.txt 2>&1 &
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

## Modifying server.py 

In the file `server.py` the `hostname` and `serverPort` should be set to: 
```
hostName = "159.65.55.208"
serverPort = 8000
```

## Building PhysLean 

If starting from a new build you will have to build PhysLean. 
There should be a more permanent fix to this, but for the time being: 

In 
```
nano Tests.lean
```
add `import PhysLean`. 
Then run 
```
lake build Tests
```

The local version of loogle can be checked with: 

```
lake exe loogle SpaceTime
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

## Getting the port to work

I updated `/etc/nginx/sites-available/loogle.physlean.com` to 
```
server {
    listen 80;
    server_name loogle.physlean.com;

    location / {
        proxy_pass http://159.65.55.208:8000;  # Replace YOUR_PORT with the port your app listens on
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
```
ALlowed 
```
sudo ufw allow 8000
```

Then made a cerficate: 
```
sudo certbot --nginx
```

Restarted nginx 
```
sudo systemctl reload nginx
```

## Fixing 502 error. 

``` 
sudo systemctl stop myserver
cd ./loogle/
export LIBRARY_PATH=/usr/lib/x86_64-linux-gnu:$LIBRARY_PATH
lake build
sudo systemctl daemon-reload;
sudo systemctl start myserver
```
Then check with 
```
sudo systemctl status myserver
```
