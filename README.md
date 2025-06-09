# Welcome to Zoltans Event Manager

## What is 'Zoltans Event Manager' ?
It consists of the frontend part, which is an Android application in which the user can subscribe to events and the event organizer can create, update, and delete those events.  
One of the bonus features is the possibility for the user to import events to their Google Calendar.  
Authentication is handled by Google, which is safe and convenient for the users and organizers.


## How is the project Structured?
the project consists of 3 parts:  
**Backend:**  
- the Postgres database to store user and event data
- the Java Spring Boot application running on a server managing requests  

**Frontend:** 
- the Kotlin Android Application where events can be managed.

## How to Install the application
**NOTE:** this repo contains two submodules, cloning this repo will not clone the submodules!
### Front End Android
1. follow this [*link*](https://github.com/Zolske/Zoltans-Evant-Manager-Frontend/tree/0a39e99cd17b5c449a2d8870e98fcf07ce3c7c47) to get to the Github repository and clone it. 

2. change into the root directory:  
`cd Zoltans-Evant-Manager-Frontend`

3. rename the file `local.properties_BLUEPRINT` to `local.properties` and move it from the app directory into the projects root directory  
`mv app/local.properties_BLUEPRINT local.properties`

4. open it and provide enter the credentials:  
`nano local.properties`  
```
WEB_CLIENT_ID=""         # provided by me

BASE_URL_BACKEND=""      # provide by me, or clone backend for local backend

ROOT_ADMIN_PASSWORD=""   # you choose the password which is going to be the password
                         # for the root user in the app
```

#### [Set up your Google Cloud Console project](https://developer.android.com/identity/sign-in/credential-manager-siwg#set-google)
*... in the mean time you can open the project in Android Studio, ...*  
For Google authentication to work, you need to register the cloned project with google. 

1. Open your project in the [Cloud Console](https://console.developers.google.com/auth/overview), or create a project if you don't already have one.
.
2. On the Client page of one of your projects or create a new project, you need to create a client with the SHA-1 signature and the apps package name.  
**name**: *what ever you like*  

**package name**: `com.kepes.zoltanseventmanagerfrontend`  

**SHA-1 certificate fingerprint**: *see instructions below*
- on your terminal run:  
`keytool -list -v -keystore ~/.android/debug.keystore -alias androiddebugkey -storepass android -keypass android`  
and enter the key into the field

3. click on **create** create
![developer console](./doc/image/Screenshot%20from%202025-06-09%2016-20-29.png)


### Backend End
- say 'hi' to the backend application by clicking on the [link](http://167.86.118.254:8080/api/auth/hello)
