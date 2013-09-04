
# superagent-retry

  A retrying layer for a superagent request, adds a `.retry` method to a request to add retrying logic to it. Will retry the request up to count times

## Usage

```javascript
var superagent = require('superagent');
require('superagent-retry')(superagent');

superagent
  .get('https://segment.io')
  .retry(2) // retry twice
  .end(onresponse);


function onresponse (res) {
  console.log(res.status, res.headers);
  console.log(res.body);
}
```

## Retrying Cases

  Currently the retrying logic checks for:

  * ECONNRESET
  * ETIMEDOUT
  * EADDRINFO
  * ESOCKETTIMEDOUT
  * superagent client timeouts
  * bad gateway errors (503s)




## License

(The MIT License)

Copyright (c) 2013 Segmentio &lt;friends@segment.io&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.