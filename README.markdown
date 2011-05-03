Marker
======

This is code from a recent workshop on Node.js

We forked a simple whiteboard app by [http://mrduncan.github.com/marker](http://mrduncan.github.com/marker), and added multiuser support via Node.js and socket.io 

Installation (OSX)
==================

Here's a quick guide to get this example up and running on your local OSX machine (if you can duplicate it for Windows, please share with us).

### 1) Install Node.JS and Socket.IO

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


### 2) Make sure you're local server is running

OSX comes standard with an Apache server. To activate it, head over to your System Preferences and choose Sharing. 

Make sure that "Web Sharing" is checked on the list (left side of the page).
Take note of your unique server address. This would be the first URL link out of the two displayed on the screen. Typically it looks someting like this (but not exactly): 

http://192.168.0.198/~yourUserName/

and sometimes: 

http://yourComputerName.westell.com/~yourUserName

(yourComputerName & yourUserName are stand-ins for your actual computer and user name)

Place the URL into your browser and make sure that you get a welcome screen from Apple.

This URL address typically points at your "Sites" folder, located in: 

/Users/yourUserName/Sites/

Changing the index.html file in that folder should affect what you see in the browser once you refresh the page.

If that's the case, you're ready for step 3.


### 3) Cloning this project to your local machine

Do you have Git installed on your machine? If not, then you're easiest path is to user the download button on the top of the page. Open up the zipped file, and copy the folder and its content into the "Sites" directory mentioned in step 2.

If you're familiar with Git, then clone this repo into a new folder in your "Sites" directory. 

You should now have a folder called "marker" somewhere in your "Sites" folder.


### 4) Change the code to your local IP address

Head over to index.html, edit it with a code edditor, and find this line: 

    <script src="http://REPLACE_THIS_WITH_YOUR_SERVER_IP:8080/socket.io/socket.io.js"></script>
    
Change REPLACE_THIS_WITH_YOUR_SERVER_IP to your local IP address found at step two. Use the bottom one from the settings page - WITHOUT YOUR USER-NAME. The correct line should look something like this:

    <script src="http://127.0.0.1:8080/socket.io/socket.io.js"></script>

(Your numbers should look different. And sometimes Apple delegages a named-IP instead of these numbers. Either way .. choose the bottom one WITHOUT your user-name)

Save the file. 


### 5) Run the server

Open up the terminal and navigate to the "marker" folder. Once there, start the Node.JS server like so: 

    node whiteboard_server.js
    
If all's well, you should see something along these lines: 

    - Your node instance does not have root privileges. This means that the flash XML policy file will be served inline instead of on port 843. This will slow down initial connections slightly.
    - socket.io ready - accepting connections


### 6) Run the clients

Two test it with one machine, you'll need to open up two different browsers. To ensure compatilibty with latest browsers, open up Chrome and Safari (latest versions please.. make sure to update first). 

In both, type in your local server address (from step 2), this time it's the one with the user name. Make sure to also add the path to your marker folder. It might look something like this: 

    http://127.0.0.1:8080/apitaru/marker
    
(Your IP numbers and user name will differ)

For extra fun, You can also type this address from other computers on your local WiFi network. 

Take a quick look at your terminal window. It should indicate that two clients have joined the server. 

Now draw in one browser, and upon releasing the mouse, the same drawing should appear in the other browser. 
