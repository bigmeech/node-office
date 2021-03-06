
# node-office

  Read and Extract Data from Open Office Documents

## Installation

    $ npm install nodeoffice

## Usage

```javascript
var NodeOffice = require("./lib/node-office");
NodeOffice.readFile("Loremipsum.docx", function (err, bodyObject) {
  if(err) throw err
  var paras = bodyObject.getParagraphs();
  var runs = [];
  var content = ""
    
  //for each paragraph
  for (var paraIndex in paras) {
    var paragraph = paras[paraIndex];
    var runs = bodyObject.getRuns(paragraph);
    for (var runIndex in runs){
      var run = runs[runIndex];
      content += bodyObject.getRunContent(run)+"\n";
    }
  }
  console.log(content)
})
```

## License

  The MIT License (MIT)

  Copyright (c) 2014 <copyright holders>

  Permission is hereby granted, free of charge, to any person obtaining a copy
  of this software and associated documentation files (the "Software"), to deal
  in the Software without restriction, including without limitation the rights
  to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
  copies of the Software, and to permit persons to whom the Software is
  furnished to do so, subject to the following conditions:

  The above copyright notice and this permission notice shall be included in
  all copies or substantial portions of the Software.

  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
  IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
  FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
  AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
  LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
  OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
  THE SOFTWARE.
