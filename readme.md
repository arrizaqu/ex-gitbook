# Gitbook documentation
* Install gitbook cli
* Install Cover
* Generated Pdf Locally
* Install autocover
	
## Install gitbook cli
```java
$ npm install gitbook-cli -g
```

## Generated Pdf Locally 
* Install npm 
* Install gitbook cli
* Add config book.json 
```java
{
  "title": "My Book",
  "description": "Description",
  "author": "Author Name",
  "gitbook": ">= 3.0.0",
  "structure": {
    "summary": "SUMMARY.md",
    "readme":"README.md"
  }
}
```
* Add config package.json
```java
{
  "scripts": {
    "docs:prepare": "gitbook install",
    "docs:watch": "npm run docs:prepare && gitbook serve"
  }
}
```
* Generated Pdf / epub 
```java
npm run docs:generate-pdf
```
or 
```java
gitbook pdf ./ ./_book/mybook.pdf
```
	
## Automatic generated 
```java
{
  "scripts": {
    "docs:prepare": "gitbook install",
    "docs:watch": "npm run docs:prepare && gitbook serve",
    "docs:generate-epub" : "gitbook epub ./ ./_book/mybook.epub",
    "docs:generate-pdf" : "gitbook pdf ./ ./_book/mybook.pdf",
    "docs:generate" : "gitbook build && npm run docs:generate-epub && npm run docs:generate-pdf"
  }
}
```

## Install autocover
* Add autocover plugin in book.json file 
```java
{
    "plugins": ["autocover"],
    "pluginsConfig": {
        "autocover": {
            // Configuration for autocover (see below) 
        }
    }
}
```

* Configuration plugin in update book.json
```java
{
    "title": "My Book",
    "author": "Author",
    "pluginsConfig": {
        "autocover": {
            "font": {
                "size": null,
                "family": "Impact",
                "color": "#FFF"
            },
            "size": {
                "w": 1800,
                "h": 2360
            },
            "background": {
                "color": "#09F"
            }
        }
    }
}
```

* note : must install "node-canvas" library in server.

## Issue 
* Running gitbook with npm and Generated Pdf Locally : (https://ssmusoke.com/tag/gitbook/) 
* autocover error, following step (NOT Solved yet):
```js
	* Installing GTK 2 and Extract to: C:\GTK
	* Installing libjpeg-turbo, example : choco install -y python2 gtk-runtime microsoft-build-tools libjpeg-turbo
	* see : https://github.com/Automattic/node-canvas/wiki/Installation---Windows
	* npm install --global --production windows-build-tools
	* set GYP_MSVS_VERSION=2015
	* npm install --msvs_version=2015
	* npm install -g canvas
```
### 

## Reference 
* https://ssmusoke.com/tag/gitbook/
* https://stefanimhoff.de/2017/i-wrote-a-book-in-gitbook/ 