# What is randomdata.sh

randomdata.sh is an online hardware random generator using heat noise as entropy source to generate high quality random number.

What you will learn:
 * Why hardware random generator are better than software one.
 * How to get your first random numbers.
 * How to check your quota.
 
## Why using a hardware random generator is better?

Computers have a really hard time to create true random number, most of the pseudo random generator generate a stream of random number based on a seed and an internal state. If somehow this state leaks it can be used to predict the upcoming numbers.

Since our generator uses Johnson noise as entropy source, there is no internal state. The entropy arises from heat energy within the silicon wafer. Electrons created during this process are independent of photons falling on the detector. These electrons are captured by the sensor array and counted as signal.

Sadly most of the time those generators are complicated and expensive to setup this is why we provide this service to the community allowing anyone to benefit from its.

## Get started

Okay so now that we know the importance of good entropy, let's see how to use the API.

As you will see, randomdata.sh provides an easy-to-use API to generate all kind of random data. All API access is over HTTPS, and accessed from https://api.randomdata.sh/v1. All data is received as a JSON object.

### Your first random numbers
#### Example of a command
```
$curl -i https://api.randomdata.sh/v1/ -d 'n=5' -d 'min=0' -d 'max=100' -d 'method=getint'
```
#### Header from the server
```
HTTP/2 200
date: Thu, 22 Nov 2018 20:31:30 GMT
content-type: application/json;charset=utf-8
set-cookie: __cfduid=d4ed2207a80301ce92678e6df9218a2df1542918690; expires=Fri, 22-Nov-19 20:31:30 GMT; path=/; domain=.randomdata.sh; HttpOnly; Secure
access-control-allow-origin: *
expect-ct: max-age=604800, report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct"
server: cloudflare
cf-ray: 47de28f57e984310-MXP
```
#### Data
```
{"BYTE_USED": 20, "DATA": [34, 56, 48, 78, 76], "EXTRA": 0, "QUOTA": 982543, "RDID": "rd.shv1#b6AxMAwmqsCm", "STATUS": "success"}
```

## Quota and limitation

To ensure a fair use of our services, you need to respect a few rules. Failure to respect them will result in ban.

Every time you use the generator to generate random data it needs to take random bytes from the entropy pool. By default everyone has a quota of 1 000 000 bytes every days. You can check your quota on the statistic page.

Try to group your requests (it’s better to send one request to download 100 numbers rather than 10 small requests of 10 numbers).

Don’t send multiple parallel requests, if you use a multi-threaded client make sure it serializes the requests.

## API license

> Our API is licensed under MIT

This describes the official randomdata.sh API v1. If you have any problems or requests, please open an [issue](https://github.com/RandomDataProject/randomdata.sh/issues).
