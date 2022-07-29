# tcpkill

Slightly modified tcpkill util ([original](http://monkey.org/~dugsong/dsniff/)), to allow for only
killing a specific number of connections.

## Compilation & Installation

First install the dependencies:

```
brew install libpcap libnet
```

Compile

```
make LDFLAGS="-lpcap -lnet -L/opt/homebrew/opt/libpcap/lib -L/opt/homebrew/opt/libnet/lib" CFLAGS="-Wall -I/opt/homebrew/opt/libpcap/include -I/opt/homebrew/opt/libnet/include"
```

> If you get compilation that includes are not found, ensure with `file /opt/homebrew/opt/libpcap` and `/opt/homebrew/opt/libnet` exist and are valid directories. If there are not, you can use `brew list libpcap` and `brew list libnet` to find where the files are located and update the `make` invocation above with the correct location for on your machine.

Install:

```
sudo tcpkill /usr/local/bin
```

## Usage

Kill by host:

```
sudo tcpkill host www.google.com
```

## Tested With

- macOS Monterey 12.0.1
- `libpcap` installed through Brew at version 1.10.1
- `libnet` installed through Brew at version 1.2

## Copyrights & Story

This is me (maoueh) writing that down from my own perspective.

This seems to have been extracted from [dsniff](http://monkey.org/~dugsong/dsniff/) which contains much
more tools and right extra dependencies that is not necessary here.

I'm quite unsure who initially trim it down. The original repository of the `tcpkill` I forked on on
GitHub is https://github.com/chartbeat/tcpkill. But weirdly, it contains commits from Allan Beaufour, funnily
his repo https://github.com/beaufour/tcpkill is a fork of https://github.com/chartbeat/tcpkill. So it's unclear
who is res

All copyright belongs to original authors, I've just tweaked the code to make it work on recent
version of OSX and libraries. I also removed a bunch of files that were not used anymore.
