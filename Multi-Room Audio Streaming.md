---
---
**Amps** with USB charger**:**
MA180
Hy-V10
Lepai LP-168AH

/usr/local/etc

**Snapcast**

`config? /etc/default/snapserver`

`SNAPSERVER_OPTS="-d -s pipe:///tmp/snapfifo?name=Radio&mode=read"`
`SNAPSERVER_OPTS="-d -s pipe:///tmp/snapfifo?name=Radio&sampleformat=48000:16:2&codec=flac`

`SNAPSERVER_OPTS='-d -s "pipe:///tmp/snapfifo?name=Mopidy&sampleformat=48000:16:2&codec=flac&mode=read" -s "airplay:///usr/bin/shairport-sync?name=Airplay&devicename=SnapcastAir&port=5000]"'`

<https://github.com/badaix/snapcast/issues/13>

**Shairport-sync**

<https://github.com/mikebrady/shairport-sync>
<http://htmlpreview.github.io/?https://github.com/mikebrady/shairport-sync/blob/master/man/shairport-sync.html>

Snapserver supports [shairport-sync](https://github.com/mikebrady/shairport-sync) with `stdout` backend.

1. Build shairport-sync with `stdout` backend: `./configure --with-stdout --with-avahi --with-ssl=openssl --with-metadata`

* Copy the `shairport-sync` binary somewhere to your `PATH`, e.g. `/usr/local/bin/`
* Configure snapserver with `-s "airplay:///shairport-sync?name=Airplay[&devicename=Snapcast][&port=5000]"`

Thanks for the post. Is it possible that you didn't compile `pipe` support? To find out, could you run the command `$ shairport-sync -V` and post the output string please?

**Ubuntu:** Personal Package Archives for Shairport Sync master and development branches are available at <https://launchpad.net/~dantheperson>. A `shairport-sync` installer package is available in Ubuntu 16.04.

/etc/shairport-sync.conf
_/usr/local/etc_/_shairport-sync.conf_ 

whereis shairport-sync

### Spotify

Snapserver supports [librespot](https://github.com/plietar/librespot) with `pipe` backend.

1. Build and copy the `librespot` binary somewhere to your `PATH`, e.g. `/usr/local/bin/`

* Valid bitrates are 96, 160, 320

**plethra.com**

pulseaudio RAOP
