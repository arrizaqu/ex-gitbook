# Gitbook documentation
* Install gitbook cli
* Generated Pdf Locally
	
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
## Issue 
* Running gitbook with npm and Generated Pdf Locally : (https://ssmusoke.com/tag/gitbook/) 

## Reference 
* https://ssmusoke.com/tag/gitbook/