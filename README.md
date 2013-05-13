#Starter kit for Ember on the mobile

This can be used as a kickstart for a HTML5 / Javascript hybrid webapp based on Ember.js

## Basic structure

You can use PhoneGap / Cordova to generate wrapper apps for your target platform. Each of these will create a web view that is pointed at index.html

The index.html file pulls in the dependencies (Ember.js, jQuery 2, Fastclick, HandleBars and Minispade), as well as the application code.

Rake Pipeline is used as the build tool to concatenate the dependencies and application code. The output of this build process is placed into the site folder. index.html pulls in thesejs files.

This repo can be used to replace the sample PhoneGap app that is created when you build a new Cordova application. Ie.. the contents of the www folder for ios PhoneGap apps, the root folder for android PhoneGap apps or the www folder for BlackBerry PhoneGap apps

## First steps, coding in your browser

You can clone this repo and then run:
rakep server

This will start up the Rake Pipeline in server mode. The default configuration builds everything you need to access http://localhost:9292/index.html in your browser. You can start developing your application straight away. As long as you keep the rakep server running, it will automatically pick up changes to application files and rebuild the contents of the site folder with your latest code / templates / css.

## Now test out your app in a simulator

Have a look at http://docs.phonegap.com/en/2.7.0/guide_getting-started_index.md.html#Getting%20Started%20Guides which has information on the dev environment necessary to create PhoneGap apps. Note this url refers to PhoneGap 2.7.0  Make sure you've got the latest version of PhoneGap

Once you have installed the requirments for your environment, you can create app wrappers for each of your target mobile operating systems.

I set up my folders like this:

/ ember_mobile_app /ember_app
                   /ios
                   /android
                   /bb
                   /win_phone_8
                   /phonegap-2.7.0

This is a top level folder to contain everything for your app. The actual code for your app is stored in the ember_app folder ( THis is where you clone this repo into). Then there are wrapper apps for each of the mobile environments sitting alongside the ember_app folder. The phonegap-2.7.0 folder contains the contents of the phonegap download

So, go ahead and download the latest phone gap and then extract it. If you are in the ember_mobile_app directory, your commands should look something like:

ditto ~/Downloads/phonegap-2.7.0.zip .
tar -xvf phonegap-2.7.0.zip
rm phonegap-2.7.0.zip

## Building an iOS wrapper

If you have a directory structure like I've described above then you can run the following command to create an iOS wrapper. This is run from the the top level ember_mobile_app directory:

./phonegap-2.7.0/lib/ios/bin/create ./ios com.example.EmberPhoneGap EmberPhoneGap

This will create an iOS wrapper in the ios folder. You can test that this wrapper is working succesfully by running the following commands from the top level ember_mobile_app directory

./ios/cordova/build
./ios/cordova/emulate

If the iOS simulator launches with the PhoneGap demo app, then you are good to go. Otherwise you might be missing some dependencies like XCode.

You just need to go into ios/www and rename your cordova-X.X.X.js file to phonegap.js  as this is the filename that index.html expects

## Develop in the browser, test in the simulator  (iOS)

Once you have your ios folder set up as described above you can go back to the / ember_mobile_app /ember_app folder, and make some changes to the app.

Make sure you're running the rakep server and you'll be able to see the changes at http://localhost:9292/index.html

Make sure that you;ve followed the last step in Building an iOS wrapper section. You've renamed the cordova-X.X.X.js file to phonegap.js ... right?  In the ios/www folder ... check!

Once you're ready to test your simulator again, you can tun the ./ios_rebuild_and_emulate.sh file.
The simulator should pop up with your modified app. If you can't run the scrit you might need to change the permissions on the file by running chmod +x ios_rebuild_and_emulate.sh

##Other mobile platforms
I've got this succesfully working aginst iOS/ Android and BB10
Hopefully I'll extend this documentation soon to include steps on setting up Android and BB10 and other target mobile operating systems. Till then it shouldn't be too tricky to figure out how to replicate this for Android and BB10. If you're struggling, ping me and I'll try add the documentation for the rest


##TODO
Steps for other mobile operating system

Repo with scripts for building full directory structure including iOS/ Android etc. etc.

Example unit tests












