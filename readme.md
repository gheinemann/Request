Request
===========

Dependencies
------------
* Class
* EventDispatcher
* Event

Example
------------
```js
function completeHandler(pEvent)
{
	console.log('completeHandler', pEvent);
}

function errorHandler(pEvent)
{
	console.log('errorHandler', pEvent);
}

/**
 * Requête correcte
 */
var url = "index.html";
var params = {};
var method = 'get';//or post
var req = new Request(url, params, method);
req.addEventListener(Event.COMPLETE, completeHandler, false);

/**
 * Requête déclenchant une erreur
 */
url = "404.html";
req = new Request(url, params, method);
req.addEventListener(Event.COMPLETE, completeHandler, false);
req.addEventListener(RequestEvent.ERROR, errorHandler, false);
```
