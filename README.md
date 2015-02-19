# polygot
Combines Microsoft Windows and POSIX shell scripts into a single cross platform script

## Installation
As a module
```shell
npm install polygot --save
```

As a program
```shell
npm install polygot -g
```

## Usage
As a module
```js
var fs = require('fs');
var polygot = require('polygot');

var polygotStream = polygot(fs.createFileStream('script.bat'), fs.createFileStream('script.sh'));
polygotStream.pipe(fs.createWriteStream('script.cmd'));
```

As a program
```shell
polygot script.bat script.sh > script.cmd
```

## Example

hello.bat
```bat
@echo off

echo Hello
```

hello.sh
```shell
#!/bin/sh

echo Hello
```

```shell
polygot hello.bat hello.sh > hello.cmd
```
