# Zen Loading Bar

Adds a mobile-style loading indicator to Zen Browser - a purple gradient bar at the top of the screen plus a subtle white fill that grows inside each tab as pages load.

### Zen Loading Bar Mod Demo
https://github.com/user-attachments/assets/b4a21bce-efa2-4c89-9c44-1645ac28ea3b

##Manual Install
# How to Create userChrome.css in Zen Browser

## Step 1 — Enable Custom Stylesheets

Go to `about:config` in the address bar and press Enter.

Search for:
```
toolkit.legacyUserProfileCustomizations.stylesheets
```
Double-click the entry to set it to `true`.

---

## Step 2 — Find Your Profile Folder

Press `Win + R` and paste:
```
%APPDATA%/zen/Profiles
```
Open the folder that ends with `.Default (release)`.

---

## Step 3 — Create the chrome Folder

Inside your profile folder, create a new folder named exactly:
```
chrome
```

---

## Step 4 — Create userChrome.css if it doesn't exists

Inside the `chrome` folder, create a new file named exactly:
```
userChrome.css
```

---

## Step 5 — Copy All the CSS from chrome.css in this repo

Copy all the CSS from chrome.css in this repo and paste it inside the userChrome.css file.

---

## Step 6 — Restart Zen Browser

Fully restart Zen Browser - close it completely from the taskbar, not just the window.

---



## Features

- **Top loading bar** - 6px gradient bar (purple → pink) sweeps across the top of the viewport during page load
- **Tab progress fill** - semi-transparent white fill grows behind the tab label for all tabs including background tabs
- **4 real progress stages** using Zen's native tab attributes (`busy`, `pendingicon`, `progress`)
- **Smooth completion** - on page load finish, bar fills to 100% then fades out
- **Compact mode support** - works correctly when the toolbar is hidden
- **Glance mode aware** - adjusts correctly for Zen Glance overlay

## Compatibility

Tested on Zen Browser v1.19.8b. Works in compact mode and fullscreen.

## How it works

The top bar uses `::before` on `.browserSidebarContainer` and reads CSS variables set by `:root:has()` selectors that detect the active tab's loading state. The tab fill targets each tab's `.tab-content::before` independently so all tabs animate simultaneously.

## Screenshots

### Top Loading Bar
![Top Loading Bar](https://github.com/shariarratul/ZenLoadingBar/raw/main/assets/Top%20Loading%20Bar.png)

### Tab Progress Bar Example
![Zen Loading Bar](https://github.com/shariarratul/ZenLoadingBar/raw/main/assets/Tab%20Progress%20Bar.png)


