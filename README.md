# curl-to-har


**curl-to-har** converts shell *curl* commands to [HAR](http://www.softwareishard.com/blog/har-12-spec/#request) request objects:

``` curl
curl --request POST --url 'http://mockbin.com/request?foo=bar&foo=baz' --header 'accept: application/json' --header 'content-type: application/json' --cookie 'foo=bar; bar=baz' --data '{"foo": "bar"}'

```


``` js
{ 
  method: 'POST',
  url: 'http://mockbin.com/request',
  httpVersion: 'HTTP/1.1',
  queryString: [ { name: 'foo', value: 'bar' }, { name: 'foo', value: 'baz' } ],
  headers: 
   [ { name: 'accept', value: 'application/json' },
     { name: 'content-type', value: 'application/json' } ],
  cookies: [ { name: 'foo', value: 'bar' }, { name: 'bar', value: 'baz' } ],
  postData: { mimeType: 'application/json', text: { foo: 'bar' } } 
}
```

# Usage

```
npm install curl-to-har
```

```
var curlToHar = require('curl-to-har');
var curlString = "curl --request POST --url 'http://mockbin.com/request?foo=bar&foo=baz' --header 'accept: application/json' --header 'content-type: application/json' --cookie 'foo=bar; bar=baz' --data '{\"foo\": \"bar\"}'"
var HAR = curlToHar(input)

console.log(HAR);

```

# Running tests

```
npm test
```

For more usage examples, check out the test directory.

--
For any errors, please submit an issue here. Pull requests are most welcome!

## Thanks

**curl-to-har** © 2016+, Yos Riady. Released under the [MIT] License.<br>
Authored and maintained by Yos Riady with help from contributors ([list][contributors]).

> [yos.io](http://yos.io) &nbsp;&middot;&nbsp;
> GitHub [@yosriady](https://github.com/yosriady)

[MIT]: http://mit-license.org/
[contributors]: http://github.com/yosriady/curl-to-har/contributors
