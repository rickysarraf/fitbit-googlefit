# Introduction
----------------------------
Export all your Fitbit data to Google Fit. 

Unlike other alternatives, such as fitnessyncer.com, this aims to offer very fine granularity for the data.

![Fitbit Steps](/screenshots/fitbit_steps.png "Fitbit steps")
![GoogleFit Steps](/screenshots/googlefit_steps.png "Google Fit steps")


# Features
----------------------------
- [x] Steps - minute level precision
- [x] Distance - minute level precision
- [x] Heart rate - second level precision
- [x] Weight
- [x] Body fat
- [x] Activities 
  - [x] Running
  - [x] Swimming
  - [x] Biking
  - [x] Volleyball
  - [x] Walking
  - [x] Badminton
  - [x] Workouts (as weightlifting)
  - [x] Others (as running) -- awaiting suggestions
- [x] Calories - minute level precision
- [ ] Floors - minute level precision
- [ ] Elevation - minute level precision
- [ ] Food logs


# Setup
----------------------------
You have to register your own Fitbit and Google Fit applications. This setup is a one time thing.

1. Install dependencies
-------------------
This is python3 application so install all the dependencies using ```sudo pip3 install -r requirements.txt```


2. Fitbit setup
-------------------
All instructions below must be performed using the same Fitbit account you want to sync with Google Fit.

- Register a new Fitbit application on [Fitbit Developers Console](https://dev.fitbit.com/apps/new)
- Use the information below:

```
Application Name : --
Description : --
Application Website : --
Organization : --
Organization Website : --
OAuth 2.0 Application Type : Personal
Callback URL : http://localhost:8080/
Default Access Type : Read-Only

Note : 
1. Use your own information for fields marked --
2. Make sure you copy the Callback URL exactly (including the last /)
```
- Hit save and make a note of ```OAuth 2.0 Client ID``` and ```Client Secret```
- ```cd /auth``` and run ```python3 auth_fitbit.py <client-id> <client-secret>```
- This opens a popup in the browser. Authenticate and done!


3. Google Fit setup
-------------------
- Go to the [Google Developers Console](https://console.developers.google.com/flows/enableapi?apiid=fitness)
- Click ```Continue```. Then select ```Go to credentials``` and select ```Client ID```
- Under Application type, select ```Other``` and hit ```Create```
- Make a note of ```client ID``` and ```client secret```
- ```cd /auth``` and run ```python3 auth_google.py <client-id> <client-secret>```
- This opens a popup in the browser. Authenticate and done!


# Usage
----------------------------
Update the ```config.ini``` with own choices and start the sync using ```python3 app.py```

Note : 
--
1. Get command line help using the -h flag. 
2. Arguments passed through command-line take higher priority over ```config.ini``` values.
