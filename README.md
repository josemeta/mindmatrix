# MindMatrix
MindMatrix is a web app that allows you to have OpenAI-powered conversations with historical figures. It was originally created by Harx. This repo is a fork by JoseMeta.

# Installation Instructions
From a new linux server (like DigitalOcean), do the following:
  
## Update System Package Repos
  
```
sudo apt update
```
  
## Install Nginx
  
```
sudo apt install nginx
```
  
## Replace default Nginx config to forward port 80 to 3000
  
```
cp ./config/default /etc/nginx/sites-available/default
```
  
## Install nodejs
  
```
sudo apt install nodejs
```
  
## Clone the MindMatrix project repo
  
```
git clone https://github.com/josemeta/mindmatrix.git
cd mindmatrix
```
  
## Install npm and all packages required by the project
  
```
npm install
```
  
## Replace "yourdomain.com" with your own domain in server.js
  
```
nano server.js
```
  
## Install pm2 so that you can run the node app as a background process
  
```
npm install -g pm2
pm2 start server.js
```
  
# More Info
MindMatrix was originally created by Harx
## Source Repo
https://github.com/harrisonr98/mindmatrix
## Join Harx's Discord Server:
https://discord.gg/J2D63mVDTC
