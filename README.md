Hello! This is the submission of DAVID TIMONERA for the Fetch Rewards SRE Exercise. Below are the instructions for installing/running the code, a section detailing my changes, and finally a section with some other notes of mine.


    Installation and Running the Exercise

1. You must have Python and the Python YAML library installed.
   1. You can install python from the [python website](https://www.python.org/downloads/)
   2. PyYAML can be installed [here](https://pypi.org/project/PyYAML/#files) or through your Python IDE.


2. You need a compatible .yml file that contains information for each endpoint. There is a sample in this repository named config.yml that will work.


3. The .yml filepath is a required argument for the program to run. You can add it as an argument in your IDE's Run configuration, or as an argument in command line.


4. Once everything is set up, simply run the program to begin monitoring the endpoint connections.


    Code Changes
1. Added constants to define our parameters:
   1. STATUS_CODE_MIN = 200
   2. STATUS_CODE_MAX = 299
   3. RESPONSE_TIME_MAX = 500000 # MICROSECONDS
   4. SLEEP_INTERVAL = 15 #SECONDS


This change was made to eliminate "magic numbers" from the code and to increase modularity in case those values are needed elsewhere.

2. Added a default value for the method variable on line 20

This change was made because the program would error out if method was type None.

3. Added the response time limit in line 27-28.

This change was added because the exercise requested that response times of more than 500ms should be counted as "DOWN"

    IMPORTANT NOTE

I saw that one request from the exercise was for the YAML format to match the sample provided.

In my testing, I found that the formatting for the body dictionaries was incorrect, and in order for the code to run, I had to remove the '' marks. AKA from '{"foo":"bar"}' to {"foo":"bar"}

I wasn't sure if I was expected to handle this in the code or not, but I opted to properly format the YAML instead.