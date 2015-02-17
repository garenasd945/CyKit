OpenViBE 0.14.0 
===============



(In Progress, Not a current working solution.)

* Install Microsoft Windows Visual C++ 9.0 (from iso)<br>

    http://download.microsoft.com/download/E/8/E/E8EEB394-7F42-4963-A2D8-29559B738298/VS2008ExpressWithSP1ENUX1504728.iso


Forum Link<br>

https://social.msdn.microsoft.com/Forums/en-US/3a77fb5c-4ef3-4fab-ba0a-91e0fe128f62/visual-c-studio-2008-express?forum=visualstudiogeneral


* Download Numpy 1.9.1 <br>
http://sourceforge.net/projects/numpy/files/latest/download?source=typ_redirect


Open Command Prompt.

* Navigate to :<br> 
```
       C:\Program Files\Microsoft Visual Studio 9.0\Common7\Tools\
```
* Run :<br> 
```
       vsvars32.bat
```

This sets the environment path for the Visual Studio compiler(s) and libraries.

*  Next. Run :<br>
```
       path > myNewPath.bat
```
* Type Path in Command Prompt and Make sure you have paths to your python folders.
  (If you do not, then edit your myNewPath.bat and add this) :<br>
```
       C:\Python27\;C:\Python27\lib\;
```
Your paths should look something similar :
```
C:\Programming\numpy-1.9.1>path
PATH=C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE;C:\Program Files\M
icrosoft Visual Studio 9.0\VC\BIN;C:\Program Files\Microsoft Visual Studio 9.0\C
ommon7\Tools;C:\Windows\Microsoft.NET\Framework\v3.5;C:\Windows\Microsoft.NET\Fr
amework\v2.0.50727;C:\Program Files\Microsoft Visual Studio 9.0\VC\VCPackages;C:
\Program Files\Microsoft SDKs\Windows\v6.0A\bin;C:\Windows\system32;C:\Windows;C
:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\python27\
;C:\python27\lib;
```

* Navigate to your Numpy1.9.1 folder and Run :<br>
```
       python.exe setup.py build
```

This will set up and configure numpy with your python installation.

* To utilize numpy simply use:<br>
```
       import numpy
```

Consult the numpy reference for additional usage.<br>
http://docs.scipy.org/doc/numpy/reference/index.html


<img src='http://blueskynet.org/edu/openvibe/acqure1.png' width=100% height=100%></img>
Figure A.

1. Select the "Generic Raw Telnet Reader" driver.
2. Set the 'Connection port' to the port you want OpenVibe to use. (ie 4444)
3. Set Sample block to 4 (mine only sends 1 sample and the picture says 16 samples)
4. Click "Driver Properties"
5. Number of Channels = 14
6. Sampling frequency = 128
7. Telnet hostname = localhost
8. Sample type = 16 bits unsigned integer
9. Apply.

<img src='http://blueskynet.org/edu/openvibe/acquire2.png' width=100% height=100%></img>
Figure B.

1. Navigate to your CyKit\RunStream.bat file and set your own custom port. (IE 21555)
2. Verify and Save.

<img src='http://blueskynet.org/edu/openvibe/acquire3.png' width=100% height=100%></img>
Figure C.

1. RunRender.bat<br>
   it should now say its connecting (or listening in this case.)
2. Click "Connect" on the OpenVIBE Acquisition server.


<img src='http://blueskynet.org/edu/openvibe/acquire4.png' width=100% height=100%></img>
Figure D.

1. Verify the Log will say "Connection succeeded!"
2. Verify Data is being read from the Python stream.py server.

<img src='http://blueskynet.org/edu/openvibe/acquire5.png' width=100% height=100%></img>
Figure E.

1. Run "OpenVIBE Designer"
2. Drag and drop "Acquisition Client" from Boxes (on the right) to the white window space on the left.
3. Drag and drop "Signal display" as well.
4. Hover over the pink arrow. "Signal Stream [signal]" drag a line from that arrow<br>
   to the green arrow "Signal [streamed matrix]" until a line connects them.
5. Double click "Acquisition Client"
6. Replace server hostname with "localhost"
7. Replace server port with your designated OpenVIBE port. (IE 4444)
8. Apply.

<img src='http://blueskynet.org/edu/openvibe/acquire55.png' width=100% height=100%></img>
Figure F.

1. Return to the "OpenVIBE acquisition server" and press "Play"

<img src='http://blueskynet.org/edu/openvibe/acquire6.png' width=100% height=100%></img>
Figure G.

1. Return to the "OpenVIBE Designer" and press "Play"

<img src='http://blueskynet.org/edu/openvibe/acquire7.png' width=40% height=40%></img>

Figure H.

1. A window will appear with your EEG stream.
2. Press Stop when completed or making signal changes.

<img src='http://blueskynet.org/edu/openvibe/acquire8.png' width=100% height=100%></img>

Figure I.

Additionally, to smooth out your EEG data.

1. Select the line between "Acquisition client" and press delete.
  (or right click and delete.)
2. Find "Signal Processing > Averaging > Signal Average"
3. Drag and Drop.
4. Connect the inputs as displayed.