#Starter kit for Ember on the mobile

This can be used as a kickstart for a HTML5 / Javascript hybrid webapp based on Ember.js

## Basic structure

You can use PhoneGap / Cordova to generate wrapper apps for your target platform. Each of these will create a web view that is pointed at index.html

The index.html file pulls in the dependencies (Ember.js, jQuery 2, Fastclick, HandleBars and Minispade), as well as the application code.

Rake Pipeline is used as the build tool to concatenate the dependencies and application code. The output of this build process is placed into the site folder. index.html pulls in thesejs files.

## First steps, coding in your browser

You can clone this repo and then run:
rakep server

This will start up the Rake Pipeline in server mode. The default configuration builds everything you need to access http://localhost:9292/index.html in your browser. You can start developing your application straight away. As long as you keep the rakep server running, it will automatically pick up changes to application files and rebuild the contents of the site folder with your latest code / templates / css.

  
