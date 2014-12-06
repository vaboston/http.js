## http.js

Make AJAX/HTTP requests from client-side JavaScript.

### Introduction

`http.js` provides a super simple, super easy way to make AJAX/HTTP requests. It's basically a few tiny functions to simplify XMLHttpRequest calls.

### Usage

`http.js` currently all HTTP methods. GET and POST requests are supported in short-hand form.

Pass in your options to the `request` function (all are optionall; defaults are shown):
```javascript
var options = {
    method: "GET",               // The method to use
    url: "./",                   // The URL to request
    async: true,                 // Whether to make the request asynchronously
    data: null,                  // Any data you'd like to send
    contentType: "text/plain",   // The MIME type of the content you're sending
    onload: function() { }       // Your onload callback function
}
```

Or use the shorthand functions `get` and `post`, which can take in a similar options object but without the need for a method.

#### Example usage

We can try a simple GET request:
```javascript
http.get({
    url: "http://reqr.es/api/users",
    onload: function() { console.log(JSON.parse(this.responseText)) }
});
```

Or a POST request:
```javascript
var data = { name: "http.js" }
http.post({
    url: "http://reqr.es/api/awesome-stuffs",
    data: JSON.stringify(data),
    contentType: "application/json",
    onload: function() { console.log(JSON.parse(this.responseText)) }
});
```

Even a random DELETE:
```javascript
http.request({
    method: "DELETE",
    url: "http://reqr.es/api/users/2",
    onload: function() { console.log(JSON.parse(this.status)) }
});
```
