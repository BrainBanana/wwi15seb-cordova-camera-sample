wwi15seb-cordova-camera-sample
------------------------------
Code Example for accessing the camera, taking a photo and display it with the Cordova Camera plugin.

Plugin: [Cordova Camera Plugin](https://github.com/apache/cordova-plugin-camera)

Based on [THIS SITE](https://www.tutorialspoint.com/cordova/cordova_camera.htm)

What it does:
-------------
There is one button added to take a picture using the native camera application and shows the recent picture on the home screen of the app.

![](https://github.com/BrainBanana/wwi15seb-cordova-camera-sample/blob/master/App.JPG)

Tested on Android Virtual Device and Android Smartphone.

Coding Snippet:
---------------

index.js:


```javascript
onDeviceReady: function() {
     this.receivedEvent('deviceready');
     document.getElementById("cameraTakePicture").addEventListener("click", cameraTakePicture);
},


function cameraTakePicture() { 
    navigator.camera.getPicture(onSuccess, onFail, {  
       quality: 50, 
       destinationType: Camera.DestinationType.DATA_URL 
    });  
    
    function onSuccess(imageData) { 
       var image = document.getElementById('myImage'); 
       image.src = "data:image/jpeg;base64," + imageData; 
    }  
    
    function onFail(message) { 
       alert('Failed because: ' + message); 
    } 
 }
 ```
## License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.
