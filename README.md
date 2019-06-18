# Filter Bubble Web Historian

This repository contains the _Web Historian_ browser extension configured for use in the _JEDS Filter Bubble_ project.

## Background

Online and mobile news consumption leaves digital traces that are used to personalize news supply, possibly creating filter bubbles where people are exposed to a low diversity of issues and perspectives that match their preferences. The [JEDS Filter Bubble](http://ccs.amsterdam/projects/jeds/) project aims to understand the filter bubble effect by performing deep semantic analyses on mobile news consumption traces. This project is a collaboration between the [VU](https://www.vu.nl/nl/index.aspx), the [UvA](http://www.uva.nl/) and [NLeSC](https://www.esciencecenter.nl/), lead by [Wouter van Atteveldt](http://vanatteveldt.com/).

Part of this project makes use of the [Web Historian](http://www.webhistorian.org/) browser extension, developed by [Ericka Menchen-Trevino](http://www.ericka.cc/). To configure this extension, the files contained in this repository can be combined with the _Web Historian_ repository, which is added as a submodule.

## Installation

## Prerequisites

- Clone the repository and its submodule using `git clone --recurse-submodules`.

## Configure the extension

- Move `manifest.json` to `community/`.
- Move `messages.json` to `community/_locales/nl/`.
- Move `config.js` to `community/js/app/`.

### Additional commands

- Run `git submodule foreach git pull origin master` to pull the latest commit for each submodule.

### Chrome

To publish the web extension on the _Chrome Store_, log into the [dashboard](https://chrome.google.com/webstore/developer/dashboard), click 'Add new item' and upload a _zip_ of the _Web Historian_ directory with the _config.js_, _manifest.json_ and _messages.json_ in place.

### Firefox

To generate an _.xpi_ _Firefox_ extension, first install [web-ext](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Getting_started_with_web-ext). Then create [API credentials](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Getting_started_with_web-ext#Signing_your_extension_for_self-distribution) and subsequently run the `web-ext sign --api-key=$AMO_JWT_ISSUER --api-secret=$AMO_JWT_SECRET` command for [self distribution](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Getting_started_with_web-ext#Signing_your_extension_for_self-distribution).

### Opera

The _Opera_ browser can install extensions from the _Chrome Store_ once a compatibility [extension](https://addons.opera.com/en/extensions/details/install-chrome-extensions/) is installed.

### Safari

To build a version of the _Web Historian_ which works with _Safari_, follow the instructions in the [Web Historian Standalone](https://github.com/Filter-Bubble/Web-Historian-Standalone) repository.

## Repository content

### Web-Historian-Community

This directory contains the [Web Historian - Community Edition](https://github.com/WebHistorian/community/) submodule which contains all the source code of the Web Historian browser extension.

### config.js

This file configures the _Web Historian_ browser extension. In particular, it sets the URL's for communication with the _Passive Data Kit_ server.

### manifest.json

The _manifest_ describes the version of the browser extension, its privileges and other things such as its icon.

### messages.json

This _JSON_ file contains all the texts used in the browser extension, adjusted for use in the Filter Bubble project.
