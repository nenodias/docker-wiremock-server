# Wiremock
Using a Postman collection you can make a POST to mock urls
[Wiremock ADMIN API](http://wiremock.org/docs/api/)

Creating a hello.json with body
```hello
{
  "request": {
    "method": "GET",
    "url": "/hello"
  },
  "response": {
    "status": 200,
    "body": "hello!"
  }
}
```


```shell
curl --data-binary "@hello.json" http://{wiremock-host}:{port}/__admin/mappings
```

So after configuring the mapping you can request.


```shell
>>> curl --data-binary "@hello.json" http://{wiremock-host}:{port}/hello
>>> hello!
```


The other methods like PUT and DELETE work as well passing the uid at the URL.
