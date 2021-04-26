# Steps (title in progress)


## Setting up the App instance
- Launch an EC2 instance with the correct version of Ubuntu
- ssh into intance
- Run the following commands:
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install nginx
systemctl status nginx [to check it's installed correctly]
```
- Go to browser and enter the public ip for the instance (this will let you see the nginx page)

### Transfering files from OS to instance
Run `scp -ri [pem file] [file/folder] ubuntu@[ip]:[path]`  
Remember to use the _absolute path_ or this command will not run

### Final setup for App
- Navigate to the folder containting `provision.sh`
- Make it executable
- Run the file with `sudo ./provision.sh`

## Extra Info
I have this code in my provision file to set up a reverse proxy:
```
sudo echo "server {
    listen 80;

    server_name _;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade \$http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host \$host;
        proxy_cache_bypass \$http_upgrade;
    }
}" | sudo tee /etc/nginx/sites-available/default
```