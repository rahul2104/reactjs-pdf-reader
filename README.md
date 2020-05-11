# React-pdf-viewer

[![NPM Version][npm-image]][npm-url]
[![Node Version][node-image]][node-url]
[![NPM Downloads][downloads-image]][downloads-url]
[![NPM License][npm-license]][npm-url]

> PDF Reader in browser for React 16.x


## Features

* **Simple**: It is very easy to use
* **Mobile-friendly**: Support all mobile terminal devices including mobile,pad and others

## Browser Support

* IE 10+
* Firefox 3.6+
* Chrome 6+
* Safari 6+
* Opera 11.5+
* iOS Safari 6.1+
* Android Browser 3+

## Quick Start

### 1. Import react-read-pdf  into your react.js project.

(You should import react firt,The version of react must be more than 16.x)

Using build tools:

```bash
npm install --save reactjs-pdf-reader
```
Using PDFReader in PC:
```js
import React from 'react';
import { PDFReader } from 'reactjs-pdf-reader';
```
Using MobilePDFReader in mobile terminal devices:
```js
import React from 'react';
import { MobilePDFReader } from 'reactjs-pdf-reader';

```
### 2. Now you have it. The simplest usage:

```js
import { MobilePDFReader } from 'react-pdf-viewer';
export default class Test extends Component{
  render(){
    return <div style={{overflow:'scroll',height:600}}>
            <MobilePDFReader url="http://localhost:3000/test.pdf"/>
           </div>
  }
}
```

```js
import ReactDOM from 'react-dom';
import Test from './test'
ReactDOM.render(<Test />, document.getElementById('root'));
```

## Documentation

react-read-pdf mainly consists of two different components. ***PDFReader and MobilePDFReader***.

### 🌱 PDFReader

```js
import { PDFReader } from 'reactjs-pdf-reader'

...
<PDFReader url={"http://localhost:3000/test.pdf"} ...>
```
####  Props in PDFReader Component 

<table>
        <tr>
            <th>Props name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
        <tr>
            <th>url</th>
            <th>string | object</th>
            <th>if url is a string, it represents absolute address or relative address of PDF files. if url is a object, you can see this <a href="#url">url object type </a> for details</th>
        </tr>
        <tr>
            <th>data</th>
            <th>string</th>
            <th>binary-like data of PDF.For example,in javascript, you can use the method "atob" to convert base64 encoded PDF to binary-like data. </th>
        </tr>
        <tr>
            <th>page</th>
            <th>number</th>
            <th>default value is 1 ,decides that which page to show in PDF file.</th>
        </tr>
        <tr>
            <th>scale</th>
            <th>number</th>
            <th>decides the viewport in render</th>
        </tr>
        <tr>
            <th>width</th>
            <th>number</th>
            <th>decides the width of viewport</th>
        </tr>
        <tr>
            <th>showAllPage</th>
            <th>boolean</th>
            <th>default value is false , if it is true , it will render all pages of the pdf file. if it is false ,it will only show the "currentPage" according to the page props's value.</th>
        </tr>
        <tr>
            <th>onDocumentComplete</th>
            <th>function</th>
            <th>after load the PDF file, in this function ,you can get some informations of the PDF file you can see this <a href="#function1">function type</a> for details</th>
        </tr>
        <tr>
            <th>getPageNumber</th>
            <th>function</th>
            <th>after load the PDF file, in this function onclick event you can get current page number of the PDF file</th>
        </tr>
    </table>
    
    
    
<a name="url"><b>url</b></a> 
the url property of ***PDFReader***

Type: 

 - string : it represents absolute address or relative address of PDF files
 - object :
 
Properties:
 Property Name| type |Description
--- | --- | ---
url | string | it represents absolute address or relative address of PDF files
withCredentials | boolean | is allow requests to carry cookie or not

<a name="function1"><b>onDocumentComplete</b></a> 
the onDocumentComplete property of ***PDFReader***

Type:

 - function(totalPage)

onDocumentComplete's type is a function, the fisrt default parameter is  totalPage of the PDF file
 
#### Notes

The url of props can be string or object.

The following two ways are the same.

One is :

```js
 <MobilePDFReader url="http://localhost:3000/test.pdf"/>

```
the other is :
```js
 <MobilePDFReader url={url:"http://localhost:3000/test.pdf"}/>

```
### 🌱 MobilePDFReader

```js
import { MobilePDFReader } from 'reactjs-pdf-reader'

...
<MobilePDFReader url={"http://localhost:3000/test.pdf"} ...>
```

####  Props in MobilePDFReader Component 
<table>
        <tr>
            <th>Props name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
        <tr>
            <th>url</th>
            <th>string | object</th>
            <th>it represents absolute address or relative address of PDF files.</th>
        </tr>
        <tr>
            <th>page</th>
            <th>number</th>
            <th>default value is 1 ,decides that which page to show in PDF file.</th>
        </tr>
        <tr>
            <th>scale</th>
            <th>'auto' | number</th>
            <th>defaut value is 'auto', react-react-pdf use pdfjs-viewer,so if the scale is 'auto' , it can Adaptive mobile device .This property decides the viewport in render</th>
        </tr>
        <tr>
            <th>minScale</th>
            <th>number</th>
            <th>defaut value is 0.25,  decides the minimum value of scale</th>
        </tr>
        <tr>
            <th>maxScale</th>
            <th>number</th>
            <th>defaut value is 10,  decides the max value of scale</th>
        </tr>
        <tr>
            <th>isShowHeader</th>
            <th>boolean</th>
            <th>defaut value is true, in order to show lively example.'react-react-pdf' added default style to  special header, you can remove this style ,if you change this value to false</th>
        </tr>
        <tr>
            <th>isShowFooter</th>
            <th>boolean</th>
            <th>defaut value is true, in order to show lively example.'react-react-pdf' added default style to  special footer, you can remove this style ,if you change this value to false</th>
        </tr>
        <tr>
            <th>onDocumentComplete</th>
            <th>function</th>
            <th>after load the PDF file, in this function ,you can get some informations of the PDF file you can see this <a href="#function2">function type</a> for details</th>
        </tr>
    </table>

<a name="function2"><b>onDocumentComplete</b></a> 
the onDocumentComplete property of ***MobilePDFReader***

Type: 

 - function(totalPage,title,otherObj)

Properties:
 Property Name| type |Description
--- | --- | ---
totalPage | number | the totalPage of the PDF file
title | title | the title of the PDF file
otherObj | object | other coding information of the PDF file

#### Notes

I strongly recommend you to set initial value of scale is 'auto',the default is 'auto' too


[npm-image]: https://img.shields.io/npm/v/reactjs-pdf-reader
[npm-url]: https://www.npmjs.com/package/reactjs-pdf-reader
[node-image]: https://img.shields.io/node/v/reactjs-pdf-reader
[node-url]: https://www.npmjs.com/package/reactjs-pdf-reader
[downloads-image]: https://img.shields.io/npm/dm/reactjs-pdf-reader.svg
[downloads-url]: https://www.npmjs.com/package/reactjs-pdf-reader
[npm-license]:https://img.shields.io/npm/l/reactjs-pdf-reader
