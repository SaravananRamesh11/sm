1.Go to the JADX folder

**cd ~/path-to-your-folder/jadx-1.5.5**

**./bin/jadx-gui**

**------------------------------------------------**

2.frida server
.	adb shell
.	su(optional)
.	cd /data/local/tmp

.	Check:

&nbsp;	ls



&nbsp;	You should see something like:



&nbsp;	frida-server



. 	Give execute permission (if you didn’t already)

&nbsp;	chmod +x frida-server



. 	Start the Frida server

&nbsp;	./frida-server \&

------------------------------------------------------------------

.	frida-ps -U(if it shows processes then ur good,**run it in different terminal**)

----------------------------------------------------------------

.	Command for bypass with js file

&nbsp;	**frida -U -f com.example.marveldroid -l bypass.js --no-pause**



	js code for hooking




	Java.perform(function() {

&nbsp;   // Reference the specific activity class

&nbsp;   var RealityStoneActivity = Java.use("com.example.marveldroid.RealityStoneActivity");



&nbsp;   // Overwrite the private securityCheck method

&nbsp;   RealityStoneActivity.securityCheck.implementation = function() {

&nbsp;       console.log("\[\*] Intercepted securityCheck in RealityStoneActivity");

&nbsp;       console.log("\[+] Forcing return value: true");

&nbsp;      

&nbsp;       // This bypasses the original 'return false'

&nbsp;       return true;

&nbsp;   };

});

---------------------------------------------------------------------





