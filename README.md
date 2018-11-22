# What is randomdata.sh

randomdata.sh is an online hardware random generator using heat noise as entropy source to generate high quality random number.

What you will learn:
 * Why hardware random generator are better than software one.
 * How to get your first random number.
 * How to use it in your application.
 * How to check your quota.

## Get started

randomdata.sh provides an easy-to-use API to generate all kind of random data.

All API access is over HTTPS, and accessed from https://api.randomdata.sh/v1. All data is received as a JSON object.

### Getting your first random number
Example of a command
```
$curl -i https://api.randomdata.sh/v1/ -d 'n=5' -d 'min=0' -d 'max=100' -d 'method=getint'
```
Response by the server
```
HTTP/2 200
date: Thu, 22 Nov 2018 20:31:30 GMT
content-type: application/json;charset=utf-8
set-cookie: __cfduid=d4ed2207a80301ce92678e6df9218a2df1542918690; expires=Fri, 22-Nov-19 20:31:30 GMT; path=/; domain=.randomdata.sh; HttpOnly; Secure
access-control-allow-origin: *
expect-ct: max-age=604800, report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct"
server: cloudflare
cf-ray: 47de28f57e984310-MXP

{"BYTE_USED": 20, "DATA": [34, 56, 48, 78, 76], "EXTRA": 0, "QUOTA": 982543, "RDID": "rd.shv1#b6AxMAwmqsCm", "STATUS": "success"}
```

### Why using a hardware random generator is better?



## API license

> Our API is licensed under MIT

This describes the official randomdata.sh API v1. If you have any problems or requests, please open an [issue](https://github.com/RandomDataProject/randomdata.sh/issues).
