# TryHackMe: [Client-Server Basics]

**Date:** August 7 2026  
**Path:** Pre-security

## What it covered

* How requests from clients are sent to servers via specific protocols and ports to get access to/retrive  information or data

## What I learned

* How data is requested and received. for example, alice sends bob to order pizza at luigi's pizza (Request) and bob comes back
with pizza (Data received.)
* Using specific languages for a server to understand and provide data
* What ports are, they are used to identify services running on systems, so to access a service, you need correct port
* What DNS(Domain Name Service) are, provides the coordinates, or IP address, for a website. 
* What the GET tool does, being to request data from a DNS and receive resources from a web server. 
## Something that tripped me up

*

## Commands / notes I want to remember
9 core commands that define HTTP(Request for comments, or RFC documents)
GET
POST
PUT
DELETE
PATCH
HEAD
OPTIONS
CONNECT
TRACE

Scheme: Tells us which protocol was used: HTTP or HTTPS.
Host: Tells us the name of the host we request resources from.
Filename: Indicates which file we requested from the host. In our request, this is "/", which actually translates to "index.html".
Address: Displays the IP address where the website is hosted. In our example, we are hosting the website on the same device. That's why the address 127.0.0.1 is shown.
Status: This field indicates whether the request was successful. In our example, we received a "200 OK" status, which means that the request was successful.

```text
```
