# OpenAIExposePythonFlaskAPIs
Flask used for exposing 2 basic methods for using open ai. Can be used for completion.

# Setup and deploy/run and stop using nohup

You can package and run the above Flask application using nohup on a Unix-like system:

* Create a new directory for your application and change to that directory:

    ```mkdir my-chatbot-app```
    ```cd my-chatbot-app```

* Copy the Flask application code into a file named app.py in the current directory.

* Install the required packages using pip:

    ```pip install flask openai```
    ```pip install flask-cors```

* Run the Flask application in development mode to test it:

    ```FLASK_APP=app.py flask run```

* Once you've confirmed that the application is working as expected, you can stop the Flask development server by pressing Ctrl+C.

* To run the Flask application as a background process using nohup, first make sure that you're in the same directory as your app.py file. Then, run the following command to start the application and redirect its output to a log file:

    ```nohup flask run > my-chatbot-app.log &```

* The nohup command ensures that the Flask application continues to run even if you log out of your shell or close your terminal window. The > symbol redirects the output of the flask run command to the specified log file (my-chatbot-app.log in this case). The & symbol at the end of the command runs the command in the background.

* To stop the background process, you'll need to find its process ID (PID) using the ps command, and then use the kill command to send a signal to the process to stop it. Here's an example:

    ```ps aux | grep flask```

* This command lists all processes containing the word flask. Look for the process ID (PID) of the flask run process, and then run:

    ```kill PID```

* Replace PID with the actual process ID that you found in the previous step.

That's it! Your Flask application should now be running as a background process on your local system, and you can access it by visiting http://localhost:5000 in your web browser (assuming that your application is listening on port 5000).
