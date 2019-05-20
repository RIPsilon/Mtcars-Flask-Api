# Mtcars-Flask-Api
For Stat 418 HW3.  
# Instructions
1. Switch your directory to the docker folder in Docker Terminal
2. Run the line docker-compose up --build
3. Open another terminal under the same directory as in step 1 and either try the following lines:  
curl http://localhost:5000/  
OR  
docker-machine ip default  
curl http://$(output from docker-machine ip default):5000    
For step 3, curl http://$1192.168.99.100:5000 is what I used
4. We are trying to predict "mpg" using the numerical variables "disp", "hp", "drat", "wt" and "qsec". Using Mazda RX4 as an example, try running the following line  
curl -H "Content-Type: application/json" -X POST -d '{"disp":"160", "hp":"110", "drat":"3.9", "wt":"2.62", "qsec":"16.46"}' "http://$1192.168.99.100:5000/predict_mpg"  
You should get a prediction value of 22.57148162261826.
5. To stop the server from running the API, just press ctrl-C in the first terminal. Make sure to see if any other docker containers are still active by running the line  
docker container ls  
and then running the line  
docker kill (insert container name here)
