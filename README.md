# React File Reader

[![Greenkeeper badge](https://badges.greenkeeper.io/GrillWork/react-file-reader.svg)](https://greenkeeper.io/)
[![Build Status](https://travis-ci.org/GrillWork/react-file-reader.png?branch=master)](https://travis-ci.org/GrillWork/react-file-reader)
[![DAVID](https://david-dm.org/grillwork/react-file-reader.svg)](https://david-dm.org/grillwork/react-file-reader)

[![NPM](https://nodei.co/npm/react-file-reader.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/react-file-reader/)

[LIVE DEMO](http://react-file-reader.herokuapp.com/)

A flexible ReactJS component for handling styled HTML file inputs.

## Install
```
npm install react-file-reader --save
```

## ChangeLog
  - 1.0.2
    - fixed an issue w/ prop-types not being available
  - 1.0.1
    - fixed issue w/ uuid4 being a devDependency
  - 1.0.0
    - initial release

## Props
### Default Props
  - fileTypes: 'image/*'
  - multipleFiles: false
  - base64: false

### Required Props
- a child element/component
  - pass in your customized element to represent your upload input
- handleFiles
  - a function to handle the selected files from the HTML input

### Optional Props
- elementId
  - set a `unique` element Id for the input element
  - if this is not set, a random UUID is generated for each input on the page.
- base64
  - a `boolean` to convert and return the files as a base64 `string`
  - multipleFile selection will return an `array` of base64 `strings`
- multipleFiles
  - a `boolean` enforce single file or multiple file selection
- fileTypes
  - React File Reader supports all [HTML input accept attributes](https://www.w3schools.com/tags/att_input_accept.asp).

## Usage
### Import React File Reader
```javascript
import ReactFileReader from 'react-file-reader';
```

### Basic Use
```javascript
handleFiles = files => {
  console.log(files)
}

<ReactFileReader handleFiles={this.handleFiles}>
  <button className='btn'>Upload</button>
</ReactFileReader>
```

#### Response
[HTML5 FileList](https://developer.mozilla.org/en-US/docs/Web/API/FileList)

### Base64
```javascript
<ReactFileReader base64={true} multipleFiles={true} handleFiles={this.handleFiles}>
  <button className='btn'>Upload</button>
</ReactFileReader>
```

#### Response
###### multipleFiles={true}
```
["data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA", "data:image/png;base64,i..."]
```

###### multipleFiles={false}
```
  "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAA..."
```

## Copyright
Copyright (c)2017 [Grillwork Inc](http://grillwork.io). See [LICENSE](https://github.com/GrillWork/react-file-reader/blob/master/LICENSE) for details.
