# lean4web and PhysLean 

A version of lean4web with PhysLean can be found at: 

[live.physlean.com](live.physlean.com)

## The server 

The server is hosted using https://www.digitalocean.com as a droplet. The following specifications are
being used: 
- Ubuntu 24.10 x64
- 2 vCPUs
- 4GB
- 50GB Disk
Some of this may be over-kill, but I found smaller servers struggle.

## The repository 

The server is based on the forked-repository:

- https://github.com/jstoobysmith/lean4web

Which has been modified to include the PhysLean project. 

## Installing necessary programs on server 

Installing `nvm`, `node` and `npm`.

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh | bash
source ~/.bashrc
nvm install node npm
```

Installing `git`: 
```
sudo apt-get install git
```

Installing `bubblewrap` 
```
sudo apt-get install bubblewrap
```

Installing `elan` 
```
curl https://raw.githubusercontent.com/leanprover/elan/master/elan-init.sh -sSf | sh
```

Installing `pm2`
```
npm install pm2@latest -g
```


## Building 

The following commands need to be run to build the server
```
git clone --recurse-submodules https://github.com/jstoobysmith/lean4web.git;
cd ./lean4web/;
npm install;
npm run build;
```
The last `npm run build` builds the Lean project and thus can take a while. 


## Hosting 

For hosting [this](https://hayksimonyan.substack.com/i/145057812/keep-your-app-always-running-with-pm-process-manager) 
note was followed (see also the [video](https://www.youtube.com/watch?v=SSLhGanxmCg)). Except the command: 
```
pm2 start your_entry_file.js
```
is replaced with 
```
PORT=8080 pm2 start npm --name "live" -- run production
```
So in particular the commands run in this phase where:
```
PORT=8080 pm2 start npm --name "live" -- run production
pm2 list
pm2 startup ubuntu
ufw enable
ufw allow ssh && ufw allow http && ufw allow https
ufw status
sudo apt install nginx

```
Then:
```
nano /etc/nginx/sites-available/default
```
where the changes needed to be made are described in the above link.

```
sudo /etc/init.d/apache2 stop
sudo systemctl restart nginx
sudo service nginx restart
sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot
sudo certbot --nginx
```
The main source for the setup was: 
    https://www.youtube.com/watch?v=SSLhGanxmCg&t=373s
