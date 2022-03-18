# Spotify Internet Radio

Create your own internet radio streaming your spotify songs. This can be usefull if you want to stream to a MPD server.

# Usage

**Configuring your server**

Create a mopidy.conf in the root of the folder

```bash
cp mopidy.example.conf mopidy.conf
```

Change `{SPOTIFY_PASSWORD}`, `{SPOTIFY_PASSWORD}`, `{SPOTIFY_CLIENT_ID}` and `{SPOTIFY_CLIENT_SECRET}` to their corresponding values

**Starting your sever**

This will run your internet radio locally

```bash
docker-compose up
```

**Control your internet radio**

You can use ncmcpp (Cheatsheet: https://pkgbuild.com/~jelle/ncmpcpp/) or any other mpd clients.

```bash
ncmpcpp
```

**Play music from anywhere that connect to your machine**

Go to `http://${YOUR_IP}:8000/mopidy

**Add the internet stream to your mpd server**

Replace MPD_HOST

```bash
LHOST=`hostname -I |  awk '{print $1;}'` ssh {MPD_HOST} 'mpc add http://${LHOST}:8000/mopidy && mpc play'
```


