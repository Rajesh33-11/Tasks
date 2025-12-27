# Create a WAR file and convert the WAR file into a Docker image.
## Create a Ec2 Server and Login

### Clone the website files from GitHub to the server.
```
git clone https://github.com/Rajesh33-11/char-webapp33.git
```
<img width="991" height="392" alt="image" src="https://github.com/user-attachments/assets/42cf8896-e423-4bda-8ae4-6a55410fa7b6" />
_________________________
```
cd char-webapp33
```
<img width="922" height="191" alt="image" src="https://github.com/user-attachments/assets/f7ccd70c-8f8f-41ee-92ea-1fc68c7c3647" />
_________________
# create WAR File
```
mvn clean package
```

<img width="1330" height="483" alt="image" src="https://github.com/user-attachments/assets/cbc4562a-3760-43e4-806e-f376de542dee" />

# Created the target folder
<img width="961" height="122" alt="image" src="https://github.com/user-attachments/assets/1265b1e7-1b6b-452e-89ca-0491babfe08d" />

# A WAR file was created inside the target folder.
<img width="1003" height="210" alt="image" src="https://github.com/user-attachments/assets/00d204c8-b730-4e71-a533-fe9f61772d47" />

---------------
# Now create a Dockerfile.
```
vim Dockerfile
```
```
FROM tomcat:9-jdk11
RUN rm -rf /usr/local/tomcat/webapps/*
COPY target/char-webapp-1.0-SNAPSHOT.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080
CMD ["catalina.sh", "run"]
```
<img width="1001" height="396" alt="image" src="https://github.com/user-attachments/assets/3c9d4de9-bada-4740-b6c4-8ae8575b2838" />

--------------
# Now create a Dockerimage
```
docker build -t Image_name files_location
```
<img width="1027" height="528" alt="image" src="https://github.com/user-attachments/assets/f7ad7c53-50f8-4de1-81ca-77b74aecaeec" />
# Verify DockerImage
```
docker images
```
<img width="947" height="225" alt="image" src="https://github.com/user-attachments/assets/c46f26cb-8c25-4b46-803a-bbec9851621b" />
____________________
# Now create a Container and Portnumber
```
docker run -itd --name container_name -p 8081:8080 image_name
```

<img width="1013" height="132" alt="image" src="https://github.com/user-attachments/assets/d05faf09-abe5-4eb3-8e7a-6b933bc9aac8" />

_______________
# Now access the application in the web browser.
<img width="512" height="102" alt="image" src="https://github.com/user-attachments/assets/b759edf0-fd07-4810-9a9e-05c0fbcccb70" />
<img width="1918" height="1026" alt="image" src="https://github.com/user-attachments/assets/9c2e7046-a3b7-4436-a292-e387561c2001" />



