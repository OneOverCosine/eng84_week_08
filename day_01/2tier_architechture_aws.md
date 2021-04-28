# Setting Up a 2-Tier Application
Using AWS - personally, I began by following [this video](https://www.youtube.com/watch?v=b1b6JTYnbjU)

## Setting up the App instance
- Launch an EC2 instance with the correct version of Ubuntu
- In this example, I'm using an ami

### Setting up Security Groups

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

## Setting up the Database instance
- Launch an EC2 instance with the correct version of Ubuntu
- ssh into intance (add more details)
- Run the following commands:
```
sudo apt-get update
sudo apt-get upgrade
```

## Connecting App to Database
- Inside the app instance run: `sudo echo "export DB_HOST=mongodb://[db_private_ip]:[port_no]/posts" >> ~/.bashrc`. This creates an environment variable we can use to connect to the database
- Then `source ~/.bashrc` to (reset something - pls look into this)

## Creating an image for App and Database
- Select the instance you'll create and image for
- Click "Actions" -> "Image and templates" -> "Create image"
- Give your image a name and description
- Click save

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