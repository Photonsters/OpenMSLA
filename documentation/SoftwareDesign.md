# OS Design

## Name Storming:
The project should have a reasonably memorable name that is unique so that search engines easily
index/find content about it.  Ideas: 
 1. SLIPI/SLIPRI - StereoLIthography P(R)inting Interface
 2. SCORPYON - SCalable Open Resin Printing YON
 3. SLINC - StereoLithography Is Not Closed (SLINC Is Not Closed)
 4. PUVRay (Photonsters UV Raycaster?)
 5. Phojektor
 6. h-Bar OS (ℏOS)
 7. ...
 
## REST API
To facilitate adoption and allow for innovation in methodology to interact with one or more machines from a single UI, we should
define a REST-like API.  The process that projects images into the vat is the "server".  The process interpreting
input from the user and/or presenting the state of the server is the "client".  A client can run anywhere.  A server is a "printer" and may
or may not also run a client or have local/internal means for a user to interact with it.

What are all the functions we need to define in this API?  This table is for brainstorming and collecting requirements.

URL | METHOD | ACTION
--- | ------ | ------
/ | GET | Return printer status datastruct
/upload?clientFilespec | POST | Upload file
/download?serverFilespec | GET | Download file
/delete?serverFilespec | DELETE | Delete file
/zhome\<?endstopID\> | PUT | Home the Z-axis
/zabs?position | PUT | Move the Z-axis to \<position\>
/zrel?distance | PUT | Move the Z-axis by \<distance\>
/zero | PUT | Set Z=0 to the current location
/set?name=value | PUT | Set any number of print(er) parameters
/print?serverFilespec | PUT | Print the specified file
/cancel | PUT | Stop the current print
/pause | PUT | Pause the current print
