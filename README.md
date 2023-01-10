# MiniProject
Android Application for Citizen Safety

We will be creating a service, and in that service, we would listen for a Shake Event by the phone. When we register a shake event i.e., when the user shakes the phone, we would send the user’s location with a predefined message to all the contacts which the user has previously added to the app. 

1) Downloading Android Studio
2) creating new project in Android Studio - select Java as the programming language.
3) Creating the Contacts Module
   a)Create a model class that will hold the data of Contact, mainly Name and Phone Number. Apart from the usual constructor and getters and setters, we have an               additional validate(String) method. This method checks if the retrieved phone number is in the correct format(+91XXXXXXXXXX) or not. If not, then it converts             the string and returns the formatted string. 
   b) Creating a Database Helper class - We need to store all the contacts, the user selects, into a Database so that it is available every time the app needs it. We               will populate the ListView with the help of this database and also at the time of sending messages, we will retrieve the contacts in a list from this database.
   c) Creating a CustomAdapter - In order to handle the data in ListView, we will need a Customised Adapter. We will add a LongClickListener on the LinerLayout so that          whenever a user wants to delete an existing item from ListView he can simply long-press that item. And in return, we would show a dialog asking for confirmation.        As the user confirms, we will also delete that item from the database too.
   d) Layout file for each item in ListView.
4)Creating the Service Module
     a)Creating ShakeDetector class -we implement the SensorEventListener which is used for receiving notifications from the SensorManager when there is a new or change         in sensor data. 
     b)Creating the SensorService - Creating a sensor service. From the commencement of Android 6, Google has included some extra security checks regarding background           services.Our main focus while building this app should be on how we can keep the service running even when the app is not running.
     c) Creating the Broadcast Receiver - Whenever a service is destroyed, the onDestroy method is called, and we will use that method to call a broadcast receiver                  before the service is actually destroyed. 
5)Working with the MainActivity.
Notes:

    1. Allow the app to autostart, in order to use the app while the screen is off.

    2. Remove any battery optimization constraints on the app. This might make Android kill the service.

    3. Allow all the permissions, especially allow location permissions by Allowing the app to use the device location all the time. This would allow the service to use the device location when the shake event is registered.
 
