# Chapter 30. Network Programming

|   |   |
|---|---|
||_

_The Net's a cross between an elephant and a white elephant sale: it never forgets, and it's always crap._

_--Nemo_

_|

A Linux system has quite a number of tools for accessing, manipulating, and troubleshooting network connections. We can incorporate some of these tools into scripts -- scripts that expand our knowledge of networking, useful scripts that can facilitate the administration of a network.

Here is a simple CGI script that demonstrates connecting to a remote server.

**Example 30-1. Print the server environment**

|   |
|---|
|#!/bin/bash
# test-cgi.sh
# by Michael Zick
# Used with permission

# May have to change the location for your site.
# (At the ISP's servers, Bash may not be in the usual place.)
# Other places: /usr/bin or /usr/local/bin
# Might even try it without any path in sha-bang.

# Disable filename globbing.
set -f

# Header tells browser what to expect.
echo Content-type: text/plain
echo

echo CGI/1.0 test script report:
echo

echo environment settings:
set
echo

echo whereis bash?
whereis bash
echo


echo who are we?
echo ${BASH_VERSINFO[*]}
echo

echo argc is $#. argv is "$*".
echo

# CGI/1.0 expected environment variables.

echo SERVER_SOFTWARE = $SERVER_SOFTWARE
echo SERVER_NAME = $SERVER_NAME
echo GATEWAY_INTERFACE = $GATEWAY_INTERFACE
echo SERVER_PROTOCOL = $SERVER_PROTOCOL
echo SERVER_PORT = $SERVER_PORT
echo REQUEST_METHOD = $REQUEST_METHOD
echo HTTP_ACCEPT = "$HTTP_ACCEPT"
echo PATH_INFO = "$PATH_INFO"
echo PATH_TRANSLATED = "$PATH_TRANSLATED"
echo SCRIPT_NAME = "$SCRIPT_NAME"
echo QUERY_STRING = "$QUERY_STRING"
echo REMOTE_HOST = $REMOTE_HOST
echo REMOTE_ADDR = $REMOTE_ADDR
echo REMOTE_USER = $REMOTE_USER
echo AUTH_TYPE = $AUTH_TYPE
echo CONTENT_TYPE = $CONTENT_TYPE
echo CONTENT_LENGTH = $CONTENT_LENGTH

exit 0

# Here document to give short instructions.
:<<-'_test_CGI_'

1) Drop this in your http://domain.name/cgi-bin directory.
2) Then, open http://domain.name/cgi-bin/test-cgi.sh.

_test_CGI_|

For security purposes, it may be helpful to identify the IP addresses a computer is accessing.

**Example 30-2. IP addresses**

|   |
|---|
|#!/bin/bash
# ip-addresses.sh
# List the IP addresses your computer is connected to.

#  Inspired by Greg Bledsoe's ddos.sh script,
#  Linux Journal, 09 March 2011.
#    URL:
#  http://www.linuxjournal.com/content/back-dead-simple-bash-complex-ddos
#  Greg licensed his script under the GPL2,
#+ and as a derivative, this script is likewise GPL2.

connection_type=TCP      # Also try UDP.
field=2           # Which field of the output we're interested in.
no_match=LISTEN   # Filter out records containing this. Why?
lsof_args=-ni     # -i lists Internet-associated files.
                  # -n preserves numerical IP addresses.
		  # What happens without the -n option? Try it.
router="[0-9][0-9][0-9][0-9][0-9]->"
#       Delete the router info.

lsof "$lsof_args" \| grep $connection_type \| grep -v "$no_match" \|
      awk '{print $9}' \| cut -d : -f $field \| sort \| uniq \|
      sed s/"^$router"//

#  Bledsoe's script assigns the output of a filtered IP list,
#  (similar to lines 19-22, above) to a variable.
#  He checks for multiple connections to a single IP address,
#  then uses:
#
#    iptables -I INPUT -s $ip -p tcp -j REJECT --reject-with tcp-reset
#
#  ... within a 60-second delay loop to bounce packets from DDOS attacks.


#  Exercise:
#  --------
#  Use the 'iptables' command to extend this script
#+ to reject connection attempts from well-known spammer IP domains.|

More examples of network programming:

1. [Getting the time from _nist.gov_](devref1.html#NPREF)
    
2. [Downloading a URL](devref1.html#NW001)
    
3. [A GRE tunnel](system.html#IPSCRIPT0)
    
4. [Checking if an Internet server is up](communications.html#PING0)
    
5. [Example 16-41](communications.html#ISSPAMMER)
    
6. [Example A-28](contributed-scripts.html#ISSPAMMER2)
    
7. [Example A-29](contributed-scripts.html#WHX)
    
8. [Example 29-1](devref1.html#DEVTCP)
    

See also the [networking commands](system.html#NETWORKSYS1) in the [System and Administrative Commands](system.html) chapter and the [communications commands](communications.html) in the [[Chapter 16. External Filters, Programs and Commands|External Filters, Programs and Commands]] chapter.
[devref1#^NPREF|Getting the time from _nist.gov_]]
    
2. [[devref1#^NW001|Downloading a URL]]
    
3. [[system#^IPSCRIPT0|A GRE tunnel]]
    
4. [[communications#^PING0|Checking if an Internet server is up]]
    
5. [[communications#^ISSPAMMER|Example 16-41]]
    
6. [[contributed-scripts#^ISSPAMMER2|Example A-28]]
    
7. [[contributed-scripts#^WHX|Example A-29]]
    
8. [[devref1#^DEVTCP|Example 29-1]]
    

See also the [[system#^NETWORKSYS1|networking commands]] in the [[system.html|System and Administrative Commands]] chapter and the [[communications.html|communications commands]] in the [[external.html|External Filters, Programs and Commands]] chapter.

