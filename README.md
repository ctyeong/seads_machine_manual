# SEADS Machine Manual  

## Running
1. Run "$ ssh user_id@ip_address"
1. Enter password
1. Run Tensorflow
  * (without Jupyter, directly to shell prompt)
    1. Run "$ nvidia-docker run -it -p port1:8888 -p port2:6006 --name name_00 -v path:/data tf:seads /bin/bash"
      * Use the allocated port numbers for "port1" and "port2"
      * Use a distinguishable name for your created container instead of "name_00" (For each run, the name should be different)  
      * "path" is the path (e.g. "/home/user_id") you want to connect to the created container, which will be located under "/data" of the container
      * Tensorboard will be available by connecting "http://ip_address:6003" in your web browser.
    1. You are now in the created container where you can use the shell just as the python virtual environment for tensorflow.

  * (with Jupyter)   
    1. Run "$ nvidia-docker run -it -p port1:8888 -p port2:6006 --name name_00 -v path:/notebooks tf:seads"
    1. Copy the letters following "/?token="
    1. Connect "http://ip_address:8003" in your web browser and enter the copied token
    1. Now you see jupyter interface

## Closing
- Push (Cntrl + c) twice in the terminal
- If you did not finish your container properly, type "$ docker container stop name_00" where "name_00" is the container's name you made when creating the container.
  - When you cannot remember the name correctly, you can list all running containers by using "$ docker container ls"

## Tip
* When you like to keep the server computer to run even after disconnected from your local computer
  1. Run "$ screen" just after the second step for < Running > and continue next steps
  1. Push (Ctrl + a, d) at any time when you want to disconnect from the ssh
  1. Run "$ screen -r" just after the second step for < Running >, when you want to return to the work

* Large HDD storage is available in "/data"
