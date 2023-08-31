# MindMatrix
MindMatrix is an immersive web application that harnesses the power of OpenAI's API to breathe digital life into iconic historical figures. Visitors can navigate to the platform, select luminaries such as Albert Einstein, and engage in real-time simulated conversations with them. Imagine chatting with Einstein, delving into his thoughts, or seeking insights—all facilitated through the capabilities of ChatGPT. Originally conceived by Harx, this repository represents JoseMeta's fork, introducing additional tweaks and features.

## Installation Instructions
To set up on a fresh Linux server (e.g., DigitalOcean), follow these steps:

### 1. Update System Package Repositories
This step fetches the latest list of available software packages for your server.
```bash
sudo apt update
```

### 2. Install Nginx
Nginx is a web server that can also be used as a reverse proxy. We'll use it to serve our application.
```bash
sudo apt install nginx
```

### 3. Install Node.js
MindMatrix is built on Node.js, which is a JavaScript runtime. We need to install it to run the app.
```bash
sudo apt install nodejs
```

### 4. Clone the MindMatrix Project Repository
Here, we're fetching the codebase of MindMatrix to our server.
```bash
git clone https://github.com/josemeta/mindmatrix.git
cd mindmatrix
```

### 5. Install npm and Project Dependencies
`npm` stands for Node Package Manager. It is the default package manager for Node.js and helps manage project dependencies. When you run a project, it might depend on libraries or other modules. These dependencies are listed in a file called `package.json` in your project directory.

The command `apt install npm` installs the npm tool itself.

The command `npm install` looks at the `package.json` file and downloads all the listed dependencies, making sure your project has everything it needs. It installs these dependencies into a folder named `node_modules` in your project directory.

```bash
# Install the Node.js package manager
apt install npm
# Install all the dependencies listed in package.json
npm install
```

### 6. Configure Domain in server.js
Your application needs to be aware of the domain it's serving. Within the `server.js` file, there's a placeholder (`"yourdomain.com"`) that you need to replace with the actual domain where you intend to deploy your application. We'll use the `nano` text editor to make this change, but you can use any editor you're comfortable with.

```bash
# Open server.js in nano editor to replace "yourdomain.com" with your actual domain
nano server.js
```

### 7. Set Up pm2 for Background Process Management
`pm2` is a process manager for Node.js applications. It helps keep the app running, even if the server restarts.
```bash
npm install -g pm2
pm2 start server.js
```

### 8. Configure Nginx to Forward Traffic
By default, Nginx listens on port 80, which is the standard port for HTTP traffic. However, our Node.js application might run on a different port (often 3000 for Node.js apps). To make sure users accessing our domain get forwarded to our application, we'll replace Nginx's default configuration with a custom one provided in our repository. This custom configuration ensures traffic on port 80 is forwarded to our application's port.
```bash
cp ./config/default /etc/nginx/sites-available/default
```

### 9. Restart Nginx Server
After making changes to its configuration, we need to restart Nginx so it recognizes and applies them.
```bash
sudo systemctl restart nginx
```

## Additional Information

MindMatrix was pioneered by Harx.
