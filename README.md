Starter project that includes the usage of Git and other CI/CD tools. 
This project is a simple Python application that uses Flask to create a basic web server. 
Using Git for version control, Jenkins for continuous integration, and Docker for containerization.
Note: This project is designed to give new entrants a good idea of how to use Git, Jenkins, and Docker in a real-world scenario. 
After this project introduce and explore more advanced topics like automated testing, deployment strategies, and infrastructure as code.

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


 


