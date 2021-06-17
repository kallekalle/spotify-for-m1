# Spotify-M1

A native Spotify desktop app for Apple Silicon, built using [Nativefier](https://github.com/nativefier/nativefier)

## Installing dependencies
### 1. [Python 3](https://www.python.org/downloads/)

 - Download and install the latest version from the website

### 2. [Node.js](https://nodejs.org/en/)

 - Download and install the latest version from the website

### 3. [Nativefier](https://github.com/nativefier/nativefier)

 - Open Terminal and type:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```npm install -g nativefier```


## Building the app

### 1. Clone project

```
git clone https://github.com/kallekalle/spotify-for-m1
```

### 2. Open Terminal and type:

```bash
cd Spotify-for-M1
nativefier "https://open.spotify.com" --name Spotify --icon icon.icns --widevine --inject spotify.js --inject spotify.css --user-agent firefox
```

Optional:
Add ```--title-bar-style hidden``` to the end of the previous command if you prefer [a hidden titlebar](https://imgur.com/a/xsHr5m8)

### 3. Install castLabs EVS

```
python3 -m pip install --upgrade castlabs-evs
```

### 4. Create an EVS account

```
python3 -m castlabs_evs.account signup
```

### 5. EVS-sign the app

```
python3 -m castlabs_evs.vmp sign-pkg Spotify-darwin-arm64
```

### 6. Verify that the app has been properly signed

```
python3 -m castlabs_evs.vmp verify-pkg Spotify-darwin-arm64
```


## Credits

Made with [Nativefier](https://github.com/nativefier/nativefier).

'Spotify.js' and 'Spotify.css' scripts taken from [Nativefier's CATALOG.md](https://github.com/nativefier/nativefier/blob/master/CATALOG.md)

EVS documentation taken from the [EVS wiki page](https://github.com/castlabs/electron-releases/wiki/EVS)

Inspired by [17hoehbr's Spotify-M1](https://github.com/17hoehbr/Spotify-M1) project
