# Infrastructure-Automation
Onboarding-Starter project that includes the usage of Git and other CI/CD tools
Starter project that includes the usage of Git and other CI/CD tools. 
This project will be a simple Python application that uses Flask to create a basic web server. Using Git for version control, Jenkins for continuous integration, and Docker for containerization.
Note: This project, to gives new entrants a good idea of how to use Git, Jenkins, and Docker in a real-world scenario. 
As they get more comfortable, we will start to explore more advanced topics like automated testing, deployment strategies, and infrastructure as code.
………………………………………………………………………………………….

Step 1: Set Up Your Development Environment
•	Install Git, Python, Flask, Docker, and Jenkins on your local machine.
•	Set up a GitHub account if you don’t already have one.
Step 2: Create a New Repository on GitHub
•	On GitHub, create a new repository.
•	Clone the repository to your local machine using git clone.
git clone https://github.com/username/repository.git
Step 3: Create a Simple Flask Application
•	In your local repository, create a new file called app.py.
•	In app.py, write a simple Flask application.
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
    return "Hello, World!"

if __name__ == '__main__':
    app.run(debug=True)

Step 4: Dockerize Your Application
•	Create a Dockerfile in your repository.
•	In the Dockerfile, write the steps to create a Docker image of your Flask application.
FROM python:3.7
WORKDIR /app
COPY . /app
RUN pip install flask
EXPOSE 5000
CMD ["python", "app.py"]

Step 5: Set Up Jenkins for Continuous Integration
•	On Jenkins, create a new job for your repository.
•	In the job configuration, set it up to pull from your GitHub repository and build whenever there’s a new commit.
•	Add a build step to build the Docker image and run tests.
Step 6: Push Changes to GitHub
•	Whenever you make changes to your application, commit them with Git and push them to GitHub.
git add .
git commit -m "Your message about the commit"
git push origin main
Step 7: Monitor Your Jenkins Job
•	After pushing changes, go to Jenkins and watch your job build.








Preparing Local Machine:
Stage 1: To install Python3 and Git on your local (Ubuntu) machine, and to create a repository on GitHub:
Step 1: Install Python3
•	Open a terminal.
•	Update the package list using the following command:
sudo apt update
•	Install Python3 using the following command:
sudo apt install python3
•	Verify the installation by checking the Python version:
python3 --version
Step 2: Install Git
•	Update the package list:
sudo apt update
•	Install Git:
sudo apt install git
•	Verify the installation by checking the Git version:
git --version
•	Configure your Git username and email using the following commands:
git config --global user.name "Your Name"
git config --global user.email "youremail@yourdomain.com"
Step 3: Create a New Repository on GitHub
•	Go to GitHub (https://github.com) and log in to your account.
•	Click the ‘+’ icon at the top right corner and select ‘New repository’.
•	Name your repository and provide a description.
•	Choose to make the repository either public or private.
•	Initialize the repository with a README if you want.
•	Click ‘Create repository’.
Now you have Python3 and Git installed on your local machine, and you’ve created a new repository on GitHub! 
Clone the repository to your local machine to start working on it.
………………………………………………………………………………………......
Stage 2:
To link your local Git installation to a repository on GitHub, you need to clone the repository to your local machine. Here are the steps:
Step 1: Open a Terminal
•	Open a terminal on your Ubuntu machine.
Step 2: Navigate to the Directory
•	Navigate to the directory where you want to clone the repository using the cd command. For example, if you want to clone the repository to your home directory, you can use:
cd ~
Step 3: Clone the Repository
•	Clone the repository using the git clone command followed by the URL of the repository. You can get the URL from the repository page on GitHub. It should look something like this:
git clone https://github.com/username/repository.git
Replace https://github.com/username/repository.git with the URL of your repository. Git installation linked to the repository on GitHub. You can now make changes to the files, commit those changes, and push them to GitHub. Remember to use git pull before you start your work to get the latest changes from GitHub.
…………………………………………………………………………………………………………………………………………………………….

Stage 3:  
The steps to install Flask, Docker, and Jenkins on an Ubuntu server:
Step 1: Update Your System First, make sure your system is up-to-date by running:
sudo apt-get update
sudo apt-get upgrade
Step 2: Install Python and Flask Flask is a Python library, so you’ll need Python installed. You can install Python and Flask with these commands:
sudo apt-get install python3 python3-pip
pip3 install flask
Step 3: Install Docker To install Docker, you can use the following commands:
sudo apt-get remove docker docker-engine docker.io containerd runc
sudo apt-get update
sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io
To verify the installation, run sudo docker run hello-world.
Step 4: Install Jenkins First, add the repository key to the system:
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
Then, append the Debian package repository address to the server’s sources.list:
echo deb http://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list
Update your local package index and then finally install Jenkins:
sudo apt-get update
sudo apt-get install jenkins

After the installation process is completed, start the Jenkins service with:
systemctl start jenkins
You can check the status of the Jenkins service using systemctl status jenkins.
You have Flask, Docker, and Jenkins installed on your Ubuntu server! Remember to configure Jenkins and Docker to fit your needs.

