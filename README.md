
# ScalaPay Merchant NPM

[![NPM Version][npm-version-image]][npm-url]

## Table of Contents
- [Install](#install)
- [Introduction](#introduction)
- [Recommendation](#recommendation)

## Install

This is a [Node.js](https://nodejs.org/en/) module available through the [npm registry](https://www.npmjs.com/).

Before installing, [download and install Node.js](https://nodejs.org/en/download/). Node.js 0.6 or higher is required.

Installation is done using the [`npm install` command](https://docs.npmjs.com/getting-started/installing-npm-packages-locally):

```sh
$ npm i scalapay
```

## Introduction

This is a node.js driver for mysql. It is written in JavaScript, does not
require compiling, and is 100% MIT licensed.

Here is an example on how to use it:

```js
var scalapay  = require('scalapay');
var scala     = scalapay.login({
  token : 'MERCHANT_TOKEN'
});

scala.testAccess(function(error, result) {
	if(error){
		console.log(error);
	else
		console.log(result);
});
```


## Recommendation

Create a config file named /config/ScalaAPI.js

```js
var scalapay = require('scalapay');

var Scala = scalapay.login({ 
  token: "MERCHANT_TOKEN" 
});

module.exports = Scala;
```

now you can use it in your other js files
```js
const scala = require('./config/ScalaAPI');

scala.testAccess(function(error, result) {
	if(error){
		console.log(error);
	else
		console.log(result);
});

scala.generateAddress(function(error, result) {
	if(error){
		console.log(error);
	else
		console.log(result);
});

scala.transfer("philip119@gmx.de","1337", function(error, result) {
	if(error){
		console.log(error);
	else
		console.log(result);
});
```



[npm-url]: https://npmjs.org/package/scalapay
[npm-version-image]: https://badgen.net/npm/v/scalapay
