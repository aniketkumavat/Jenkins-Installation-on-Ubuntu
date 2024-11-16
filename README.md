# Jenkins-Installation-on-Ubuntu

  This installation is specific to systems operating on Ubuntu.   Follow the below steps:  https://www.jenkins.io/doc/book/installing/linux/

Step 1: Install Java

	$sudo apt update	- done

	java -version -verify

sudo apt install openjdk-17-jre-headless  

sudo apt install openjdk-17-jdk-headless   ------- jdk is mandatory to compile the java code

sudo apt install fontconfig openjdk-17-jre - jenkins documentation said


java -version

openjdk version "17.0.8" 2023-07-18
OpenJDK Runtime Environment (build 17.0.8+7-Debian-1deb12u1)
OpenJDK 64-Bit Server VM (build 17.0.8+7-Debian-1deb12u1, mixed mode, sharing)


-------------------------

Step 2: Add Jenkins Repository i.e key

copy from site--

sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key		- done


  Step 3: Add Jenkins repo to the system i.e source list

echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null		 	- done


Step 4: Install Jenkins
	sudo apt-get update 		-done

	$ sudo apt install jenkins		- done

	to login inside jenkins we need password

	Get the initial admin password  from command
	sudo cat  /var/lib/jenkins/secrets/initialAdminPassword			


Step 5: Verify installation

You can enable the Jenkins service to start at boot with the command:

sudo systemctl enable jenkins		- done

sudo systemctl start jenkins		-done

sudo systemctl status jenkins	- jenkins is running		done


Step 6: Once Jenkins is up and running, access it from the
link: http://localhost:8080    or the IP of virtual machine like xx.xx.xx.xx:8080		done

Start, Stop & Restart Jenkins

	$ sudo service jenkins restart
	$ sudo service jenkins stop
	$ sudo service jenkins start
