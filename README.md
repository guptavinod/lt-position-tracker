# Location Tracker position-tracker

## Make sure position-simulator is running before position-tracker

## TEST APPLICATION 

1. Build Docker Image of position-tracker  
2. Create network (if not already created) --> docker network create locationtracker

3. RUN mongo db container:   
docker run -d --network locationtracker --name mongodb -p 27017:27017 mongo:3.6.5-jessie
   
4. RUN position tracker application:   
docker run -d --network locationtracker -p 8090:8090 --name positiontracker --env spring.activemq.broker-url=tcp://myqueue:61616 --env fleetman.position.queue=positionQueue --env spring.data.mongodb.host=mongodb guptavinodkumar/position-tracker:0.0.1-RELEASE



## SETTING UP GIT REPO
2.  git init
3. Go to Github and create repository lt-position-tracker
4. git remote add origin https://github.com/guptavinodkumar/lt-position-tracker.git
5. git add .
6. git commit -m""
7. git push --set-upstream origin master
