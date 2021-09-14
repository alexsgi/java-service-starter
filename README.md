# java-service-starter
Create a systemd service to start a JAR!
Tested on Ubuntu, Debian and Raspbian.

## Install

Open a terminal or sign in via SSH.
Change the directory:

    cd /usr/local/bin
    
Download the repository:

    git clone https://github.com/alexsgi/java-service-starter
    
Change directory:

    cd java-service-starter
    
Move service file to systemd folder:

    mv java-service-starter.service /lib/systemd/system/
    
Set correct permissions:

    chmod +x service-starter.sh
    chmod +x servicetester.jar
    chmod ugo+rw .

Reload the daemon:

    systemctl daemon-reload
    
You are ready to go!

Start/stop/reload the service:

    systemctl java-service-starter start|stop|reload
---

Output and errors will be printed into output.out.

    cat output.out

If you should run into an error during the install just check the service logs with

    journalctl -u java-service-starter -f

### **What you can customize**

Some things that don't have to stay like they are:
 - the name of the service: change the name of the .service file and the value of SERVICE_NAME in service-starter.sh 
 - the JAR you want to start: store your own JAR toinjava-service-starter and adapt the paths in service-starter.sh
 - the PID: change the PID in service-starter.sh
 - **the user, which starts the shell script**: in java-service-starter.service
