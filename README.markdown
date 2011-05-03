Marker
======

This is code from a recent workshop on Node.js

We forked a simple whiteboard app by [http://mrduncan.github.com/marker](http://mrduncan.github.com/marker), and added multiuser support via Node.js and socket.io 


Installation (OSX)
==================

Here's a quick guide to get this example up and running on your local OSX machine (if you can duplicate it for Windows, please share with us).

** 1) Install Node.JS and Socket.IO **

The first task is to get Node.js installed on your machine. The easiest way we found is to download [the file here] (https://sites.google.com/site/nodejsmacosx/) 

Once it's on your machine, just double click and follow the simple menu instructions. It installed Node.JS, and as important, the Node Package Manager (NPM). 

NPM allows you to quickly add new plug-in libraries to node. One of them is Socket.IO, which allows us to create a socket to stream data in realtime. 

Lets installed Socket.IO, it'll give us a chance to also ensure the NPM is doing it's thing. Fire up your Terminal window and type this: 

    npm install socket.io

It'll take a moment, and you should see something line this in response: 

    npm info it worked if it ends with ok
    npm info using npm@0.3.18
    npm info using node@v0.4.7
    npm info preinstall socket.io@0.6.17
    npm info install socket.io@0.6.17
    npm info postinstall socket.io@0.6.17
    npm info predeactivate socket.io@0.6.17
    npm info deactivate socket.io@0.6.17
    npm info postdeactivate socket.io@0.6.17
    npm info preactivate socket.io@0.6.17
    npm info activate socket.io@0.6.17
    npm info postactivate socket.io@0.6.17
    npm info build Success: socket.io@0.6.17
    npm ok
    
Also, just to make sure all's well, type this into the terminal: 

    node -help
    
If you get a long list of commands, then you're all set to go. Otherwise, you'll need to dig deeper into documentations for installing node, and figure out what the issue was. A good place to start is [here] https://github.com/joyent/node/wiki/Installation


** 2) Make sure you're local server is running **

OSX comes standard with an Apache server. To activate it, head over to your System Preferences and choose Sharing. 

Make sure that "Web Sharing" is checked on the list (left side of the page).
Take note of your unique server address. This would be the first URL link out of the two displayed on the screen. Typically it looks someting like this (but not exactly): 

http://192.168.0.198/~yourUserName/

and sometimes: 

http://yourComputerName.westell.com/~yourUserName

(yourComputerName & yourUserName are stand-ins for your actual computer and user name)

Place the URL into your browser and make sure that you get a welcome screen (anything but an error page means you're probably ok).

This URL address typically points at your "Sites" folder, located in: 

/Users/yourUserName/Sites/

Changing the index.html file in that folder should affect what you see in the browser once you refresh the page.

If that's the case, you're ready for step 3.


** 3) Cloning this project to your local machine **

Do you have Git installed on your machine? If not, then you're easiest path is to user the download button on the top of the page. Open up the zipped file, and copy the folder and its content into the "Sites" directory mentioned in step 2.

If you're familiar with Git, then clone this repo into a new folder in your "Sites" directory. 
 
