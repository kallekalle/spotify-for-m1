# Spotify-M1

A native Spotify desktop app for Apple Silicon, built using [Nativefier](https://github.com/nativefier/nativefier)

## Installing dependencies
### 1. [Python 3](https://www.python.org/downloads/)

 - Download and install the latest version from the website. Python is required for signing the app

### 2. [Node.js](https://nodejs.org/en/)

 - Download and install the latest version from the website. Node.js is used for installing Nativefier.

### 3. [Nativefier](https://github.com/nativefier/nativefier)

 - Open Terminal and type:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;```npm install -g nativefier```


## Building the app

### 1. Clone project

```
git clone https://github.com/kallekalle/spotify-for-m1
```

### 2. Navigate to the directory

```
cd Spotify-for-M1
```

### 3. Build the app:

```
nativefier "https://open.spotify.com" --name Spotify --icon icon.icns --widevine --inject spotify.js --inject spotify.css --user-agent firefox
```

Optional:
Add ```--title-bar-style hidden``` to the end of the command if you prefer [a hidden titlebar](https://imgur.com/a/xsHr5m8)

### 4. Install castLabs EVS

```
python3 -m pip install --upgrade castlabs-evs
```

### 5. Create an EVS account

```
python3 -m castlabs_evs.account signup
```

### 6. EVS-sign the app

```
python3 -m castlabs_evs.vmp sign-pkg Spotify-darwin-arm64
```

### 7. Verify that the app has been properly signed

```
python3 -m castlabs_evs.vmp verify-pkg Spotify-darwin-arm64
```

### 8. Locate the app

Navigate to

```
/Users/[user]/spotify-for-m1/Spotify-darwin-arm64
```

and run the Spotify app.

Optional:
Create a shortcut and move it to your dock/desktop/apps folder etc.

## Credits

Made with [Nativefier](https://github.com/nativefier/nativefier).

'Spotify.js' and 'Spotify.css' scripts taken from [Nativefier's CATALOG.md](https://github.com/nativefier/nativefier/blob/master/CATALOG.md)

EVS documentation taken from the [EVS wiki page](https://github.com/castlabs/electron-releases/wiki/EVS)

Inspired by [17hoehbr's Spotify-M1](https://github.com/17hoehbr/Spotify-M1) project
