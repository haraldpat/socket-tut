##THERE are two ways to run this
#(1) Way 1:
--There is already the docker-compose.yaml file.
--Just,run the command
docker-compose up
--And, it will start running.

#(2) Way 2:
--Go to client directory 
cd client
docker build -t sockettut-client .
--Go back to server directory
cd server
docker build -t sockettut-server .
--And then finally run their images, once their images are created by above commands
docker run -p 3000:3000 sockettut-client 
docker run -p 3001:3001 sockettut-server 
--And, there you go running with this app.
