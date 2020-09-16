
# How to install?
<b>Follow the instructions...</b><br>
<b>If you have Android - download <a href="https://play.google.com/store/apps/details?id=com.termux&hl=ru">Termux from Google Play</a> and open it and write the commands below:<br>
• <code>apt update</code><br>
• <code>apt upgrade -y</code><br>
• <code>apt install python -y</code><br>
• <code>apt install git -y</code><br>
• <code>git clone https://github.com/Mr-X-01/noisy</code><br>
• <code>pip install requests</code><br>
• <code>cd noisy</code><br>

# How to start?
• <code>python noisy.py --config config.json</code><br>

### Dependencies

Install `requests` if you do not have it already installed, using `pip`:

```
pip install requests
```

### Usage

Clone the repository
```
git clone https://github.com/1tayH/noisy.git
```

Navigate into the `noisy` directory
```
cd noisy
```

Run the script

```
python noisy.py --config config.json
```

The program can accept a number of command line arguments:
```
$ python noisy.py --help
usage: noisy.py [-h] [--log -l] --config -c [--timeout -t]

optional arguments:
  -h, --help    show this help message and exit
  --log -l      logging level
  --config -c   config file
  --timeout -t  for how long the crawler should be running, in seconds
```
only the config file argument is required.

###  Output
```
$ docker run -it noisy --config config.json --log debug
DEBUG:urllib3.connectionpool:Starting new HTTP connection (1): 4chan.org:80
DEBUG:urllib3.connectionpool:http://4chan.org:80 "GET / HTTP/1.1" 301 None
DEBUG:urllib3.connectionpool:Starting new HTTP connection (1): www.4chan.org:80
DEBUG:urllib3.connectionpool:http://www.4chan.org:80 "GET / HTTP/1.1" 200 None
DEBUG:root:found 92 links
INFO:root:Visiting http://boards.4chan.org/s4s/
DEBUG:urllib3.connectionpool:Starting new HTTP connection (1): boards.4chan.org:80
DEBUG:urllib3.connectionpool:http://boards.4chan.org:80 "GET /s4s/ HTTP/1.1" 200 None
INFO:root:Visiting http://boards.4chan.org/s4s/thread/6850193#p6850345
DEBUG:urllib3.connectionpool:Starting new HTTP connection (1): boards.4chan.org:80
DEBUG:urllib3.connectionpool:http://boards.4chan.org:80 "GET /s4s/thread/6850193 HTTP/1.1" 200 None
INFO:root:Visiting http://boards.4chan.org/o/
DEBUG:urllib3.connectionpool:Starting new HTTP connection (1): boards.4chan.org:80
DEBUG:urllib3.connectionpool:http://boards.4chan.org:80 "GET /o/ HTTP/1.1" 200 None
DEBUG:root:Hit a dead end, moving to the next root URL
DEBUG:urllib3.connectionpool:Starting new HTTPS connection (1): www.reddit.com:443
DEBUG:urllib3.connectionpool:https://www.reddit.com:443 "GET / HTTP/1.1" 200 None
DEBUG:root:found 237 links
INFO:root:Visiting https://www.reddit.com/user/Saditon
DEBUG:urllib3.connectionpool:Starting new HTTPS connection (1): www.reddit.com:443
DEBUG:urllib3.connectionpool:https://www.reddit.com:443 "GET /user/Saditon HTTP/1.1" 200 None
...
```

## Build Using Docker

1. Build the image

`docker build -t noisy .`

**Or** if you'd like to build it for a **Raspberry Pi** (running Raspbian stretch):

`docker build -f Dockerfile.pi -t noisy .`

2. Create the container and run:

`docker run -it noisy --config config.json`

