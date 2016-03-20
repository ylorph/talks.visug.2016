Let's built some messaging tooling just to get a sense of what is under there  
 What does it take to build a messaging system ?   
 shamelessly taking idea from the ZeroMq Book some code


FileMq (File being one of the oldest kind of messaging in computing)

Dropbox Pattern

**_Fully Decentralized_**

Multicast   

{subsection}

Distributed :   

APi Design

Both Client and Server

{subsection}

filemq-protocol = open-peering *use-peering [ close-peering ]

open-peering    = C:OHAI *( S:ORLY C:YARLY ) ( S:OHAI-OK / error )

use-peering     = C:ICANHAZ ( S:ICANHAZ-OK / error )  
                / C:NOM  
                / S:CHEEZBURGER  
                / C:HUGZ S:HUGZ-OK  
                / S:HUGZ C:HUGZ-OK  

close-peering   = C:KTHXBAI / S:KTHXBAI  

error           = S:SRSLY / S:RTFM  


{subsection}

Majordomo  
(kind of pub/sub with durable messaging)
reliable

{subsection}

Reliable ?  

{subsection}

Reliable ?  
Application Code Crashes  

{subsection}

Reliable ?  
Application Code Crashes  
System Code Crashes  

{subsection}

Reliable ?  
Application Code Crashes  
System Code Crashes  
Message queues can overflow  

{subsection}

Reliable ?  
Application Code Crashes  
System Code Crashes  
Message queues can overflow and loose messages  

{subsection}

Reliable ?  
Application Code Crashes  
System Code Crashes  
Message queues can overflow and loose messages  
Networks  fails

{subsection}

Reliable ?  
Application Code Crashes  
System Code Crashes  
Message queues can overflow and loose messages  
Networks  fails

{subsection}

Reliable ?  
Application Code Crashes  
System Code Crashes  
Message queues can overflow and loose messages  
Networks  fails
Networks  fails in strange ways  

{subsection}

Reliable ?  
Application Code Crashes  
System Code Crashes  
Message queues can overflow and loose messages  
Networks  fails
Networks  fails in strange ways  
Entire data centers can fail   

{subsection}
Reliability Redefined  
"keeping things working properly when code freezes or crashes"

{subsection}
Reliability Redefined  
"keeping things working properly when code freezes or crashes"

Request-reply:
if the server dies, the client can figure that out because it won't get an answer back.

{subsection}
Reliability Redefined  
"keeping things working properly when code freezes or crashes"

Pub-sub:
if the client dies (having gotten some data), the server doesn't know about it.

Pub-sub doesn't send any information back from client to server.
But the client can contact the server out-of-band,
"please resend everything I missed".

{subsection}
Reliability Redefined  
"keeping things working properly when code freezes or crashes"

Pub-sub:
if the client dies (having gotten some data), the server doesn't know about it.

Pub-sub doesn't send any information back from client to server.
But the client can contact the server out-of-band,
"please resend everything I missed".
