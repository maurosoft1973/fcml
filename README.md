# Firebase Cloud Message for Linux (FCML)
This tool allows you to send a notification to an android phone directly from the command line from your linux system.

## Requirements
	libcurl dev library
	unzip tool

## Compiling and Install
	make all

## Compiling and Install (only Debian)
	make all-debian

## Usage
	fcml [options]

Options are:
* -t Notification Title or (--title=)
* -m Notification Message or (--message=)
* -s Token Device or (--tokendevice=)
* -k Server Key or (--serverkey=>)
* -d Debug Mode or (--debug=1)
* -f Path of the Configuration File or (--configuration=)

The structure of configuration file is:  

[general]  
apiserver={apiserver}  
device={device}  
	
{apiserver} is the server key by Firebase Cloud Messaging

Server Key can be found in:

1. Firebase project settings
2. Cloud Messaging
3. then copy the server key

{device} is the token Device

fcml outputs JSON data to **stdout**.

## Example of Usage
	fcml -f /etc/fcml.conf -t "Hello Title" -m "Hello Message"

	or

	fcml -t "Hello Title" -m "Hello Message" -s "TokenDevice" -k "ServerKey"
