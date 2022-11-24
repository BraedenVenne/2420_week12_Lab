# 2420_week12_Lab

## Authors
- Braeden Venne
- Eric Cao

## Setup
Create a new droplet
Follow the setup video provided in week 10.
Give your droplet the following name:

- **web-one**

These will be the hostname for your server.

### Installing NGINX
1. Update local package index
   
   ![picture of apt update command](/images/aptupdate.PNG)
   
2. install *nginx* 
    
    ![picture of install nginx command](/images/installnginx.PNG)


### Making an HTML document
1. In your WSL, make an index.html file

Example html file:
```
<!DOCTYPE html>
<html lang="en">
<html>
    <head>
        <meta charset="UTF-8" />
        <title>2420_week12_Lab</title>
    </head>
    <body>
        <h1>Hello</h1>
        <h2 style="color:blue;">This is a Webpage Created By:</h2>
        <ul>
            <li>Braeden Venne</li>
            <li>Eric Cao</li>
        </ul>
    </body>
</html>
```

### Making an nginx Server Block
1. In your WSL, create a file with the Digital Ocean droplet's ip address as the name

*Note: Change the IP addresses in the example with your Digital Ocean droplet's IP address*

Example Serivce Block:
```
server {
        listen 80;
        listen [::]:80;

        root /var/www/164.92.111.93/html;
        index index.html;

        server_name 164.92.111.93;

        location / {
                try_files $uri $uri/ =404;
        }
} 
```
