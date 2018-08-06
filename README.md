Python Uber Project
==============================
Ricardo Henriques

What Is This?
-------------

This is a simple development environment that uses a Python/Flask application developed by Uber to demonstrate testing and production environments within an automation pipeline.

The first part of the pipeline involves GitHub, where you and other developers will pull and push individual versions of the project. We can configure GitHub with a webhook that references our Jenkins domain.

With webhooks, we can use Jenkins to listen for whenever there is a push to the master branch on GitHub. When there is a push, Jenkins will take the project and run a test job that is defined in the build section.

If the test passes and the build is stable, a second Jenkins job will be triggered that is responsible for deploying the project AWS. To do this, we use a pre-made AMI that contains the environment that we want to run the app on.


How To Use This
---------------

1. Navigate over to https://github.com/RickFord117/Sparta_Global_Python_App, and download a copy of the repo.
2. Cd into the repo folder on your machine and enter the command `vagrant up`.
3. When the vagrant machine has finished running, enter the command `vagrant ssh` to start the ubuntu virtual machine and then cd into the root (/) directory, then cd into the app folder to beginning developing the software.


Testing
-------

1. To run the app for testing purposes, Run `pip install -r requirements.txt` to install dependencies so that you can run the command `python app.py` successfully.
2. You will see that the app is running on `http://127.0.0.1:7000`. Enter `development.local/` into your browser URL to see the app running.
