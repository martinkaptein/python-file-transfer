# python-file-transfer

A very simple and insecure tool to transfer files between devices on a local network.

This mainly uses code found [here](https://gist.github.com/amdei/7a83e61373a040697e48), so it's not by me.

This uses the standart Python3 http.server with added Upload capability.

# Why Python file transfer

I created this fork mainly for myself, in order to transfer files between my computer (which can be any Operating System as long as it has Python 3 installed) and any device with a (any) web browser on the local network. For example when I want to transfer files to and from my old BBOS 6 or web-os phone. It should work with any device with WLAN and a web browser.  

The reason I am keeping this tool **insecure** is the fact, that I want it to work with any device, without any hassle with certificates and authentication. The idea is to make this tool as basic and backwards-compatible as possible.

# Usage

## Installation

First of all, make sure you have Python 3 installed on your system.

Then (in terminal) run:

```
git clone https://github.com/martinkaptein/python-file-transfer.git
cd python-file-transfer
```

You can run the script by simply typing `python ftranfer.py` (or `python3 ftransfer.py` if you have both Python 2 and Python 3 installed, like on OSX).

**However**, it is handy to make a view adjustments, to make this tool even more usable:

Make the file executable: `chmod ugo+x ftransfer.py`

And copy it to /usr/local/bin (while renaming it to ftransfer):

`cp ftransfer.py /usr/local/bin/ftransfer`

If that fails, use: `sudo cp ftransfer.py /usr/local/bin/ftransfer` 

If you are on Windows you will have to modify the first line of the `ftransfer.py` script to point to your Python 3 installation and use the Windows way of making a script executable and put in in your $Path.


Now you can run ftransfer from any directory from the terminal by just running `ftransfer`.

## Connecting from different devices

Now that you have ftransfer installed and running it should be accessible from any device from within your local network. For that, you need to know your local IP.

To find that out run `ifconfig` if you are on UNIX or `ipconfig` if you are on Windows.
Note your IP adress (let's say it is 192.168.178.19).

Now you can connect from any device on the local network (that has a web browser) by just navigating to:

http://192.168.178.19:8000/

To stop the server just hit ctrl+c.