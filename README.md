#Name
pnotify - A simple, portable Perl script for sending DNS NOTIFY packets with TSIG support.

#Synopsis
```
pnotfy [options]

--zone=ZONE             The DNS zone
--class=CLASS           The class (default IN)
--server=HOST           Host to send the packet to
--port=PORT             Destination port to send the packet to (default 53)
--timeout=TIMEOUT       Timeout in seconds (default 1)
--tsig-name=NAME        Optional TSIG name
--tsig-key=KEY          Optional TSIG KEY (only HMAC-MD5 is supported)
--source=ADDR           Use this source address (optional)
--help                  Show this help
```
#Output
pnotify will print either the rcode of the server response or "TIMEOUT" to STDOUT.

#Exit Code
For a successful transaction (rcode=NOERROR), the exit code will be 0. For all other outcomes it will be 1.

#Rationale
It is sometimes useful to be able to manually send a NOTIFY packet to aDNS server. There are other tools to do this (eg nsd-notify(8)) but they are not as portable as pnotify, which is a pure Perl script with only a limited range of prerequisites.

#Requirements
* Net::DNS (install with sudo apt-get install libnet-dns-perl on debian or ubuntu.)
* Getopt::Long
* Pod::Usage

#Copyright
Copyright 2011 CentralNic Ltd. This program is Free Software, you can use it and/or modify it under the same terms as Perl itself.

#See Also
* Net::DNS
* https://www.centralnic.com/

