![[Screenshot 2023-04-25 at 10.56.05.jpg]]
# Definition
Algorithm for communication between two or more parties
Defines rules for communication
Provides a service
	Algorithm -> protocol
	Function signature -> service
## Examples of protocols
STP
HTTP
SSL/TLS
WPA: encryption for wifi communication
TCP/UDP

# Classifying Protocols: Layers
Provide levels of abstraction: when working on a layer only that layer has to work, you are not responsible for the other layers. 
each layer provides a service but only to the layer above
![[Screenshot 2023-04-24 at 12.01.12.jpg]]

## Network layers
same layers on multiple machines
Lowest one does actual communication
![[Screenshot 2023-04-24 at 12.03.12.jpg]]
Has to have the same layers to be able to communicate with each other. 

### Illusion of direct communication 
![[Screenshot 2023-04-24 at 12.06.45.jpg]]

# Different Layers
## Physical layer
send one bit via physical medium ("link") e.g. ethernet, wireless
## Data link layer
Send a sequence of bits over a link reliably. make sure bits are correct and all received. Check bit flips and completeness
## Network layer
Send data from one computer in a network to another
(e.g. home network, company network, internet)
## Transport layer
Send data reliably or unreliably over an unreliable network
Everything that the transport layer does, happens on the receiver. 
## Application layer
Send application-specific information over network
![[Screenshot 2023-04-24 at 12.15.26.jpg]]
## Missing layers
Presentation and session 
are not separate from application and transport layer
presentation layer is handled by the application
session is handled partially by transport and partially by application. 
![[Screenshot 2023-04-24 at 12.15.51.jpg]]
# Sending message
## Msg Host A
![[Screenshot 2023-04-24 at 12.16.20.jpg]]
## Msg on router
![[Screenshot 2023-04-24 at 12.17.49.jpg]]
Could change information about errors within data
## Msg Host B
![[Screenshot 2023-04-24 at 12.18.45.jpg]]