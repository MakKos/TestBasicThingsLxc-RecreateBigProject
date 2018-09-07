## Challenge
Your program will get some html written to stdin. Convert all the inner html to upper-case for elements with a class name of "loud".

You can use [`trumpet`](https://npmjs.org/package/trumpet) and [`through`](https://npmjs.org/package/through) to solve this adventure.

## Explanation
Make sure to `npm install trumpet through` in the directory where your solution file lives.

With `trumpet` you can create a transform stream from a css selector:

    var trumpet = require('trumpet');
    var fs = require('fs');
    var tr = trumpet();
    fs.createReadStream('input.html').pipe(tr);
    
    var stream = tr.select('.beep').createStream();

Now `stream` outputs all the inner html content at `'.beep'` and the data you write to `stream` will appear as the new inner html content.