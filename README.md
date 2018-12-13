# Docker-Volume-mount

Intention:

I need to share a folder ( folder with the zip files that are randomly generate by running service ) with 2 (or) more containers .
	
Please look at the block-diagram
	
Block-diagram ![image](https://github.com/Sun-Raise/Docker-Volume-mount/blob/master/basic-volume-diag.PNG)
	
Create a folder on server :

Mkdir -p /opt/nginx

Create a index.html file
	        
Create & Run Nginx container :

   - docker run -t -d -p 80:80 -v /opt/nginx:/usr/share/nginx/html/offline:ro --name [conatiner-name] [image-name]
		
   - Access :  hostname/offline/index.html
	
Create & Run NodeJs container :

   - docker run -t -d -p 8080:80 -v /opt/nginx:/usr/share/nginx/html --name [conatiner-name] [image-name]
		
   - Access :  hostname/index.html
