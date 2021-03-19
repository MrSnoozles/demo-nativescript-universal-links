# Bug when compiling for production

This repository is just showcasing a bug in https://github.com/nativescript-community/universal-links version 2.0.2.

**Problem:**
The `registerUniversalLinkCallback` 


**Steps to see how it works (in development):**
* Checkout the repository
* Run with `ns run android`
* open https://www.beachup.app/share/place/xyz
-> you should see a console output and an alert

**Steps to reproduce the bug (in production):**
* Checkout the repository
* Run with `ns run android --env.production`
* open https://www.beachup.app/share/place/xyz
-> nothing happens
