# Middleware to cache request in node apps

This module caches all GET and HEAD request and it expires everything in the cache when it receives a POST, PUT, DELETE or PATCH request.
The results are cached in a Redis Database.


## Installation

```

npm install --save microservice-cache-middleware

```

## Configuration

Add this library as a middleware in your app.
Example:

```

    app.use(require('microservice-cache-middleware')({
        prefix: 'dataset',
        redisUrl: process.env.REDIS_URL
    }));

```
Config params:

| name | description | type | defaultValue | required |
|---|---|---|---|---|
| prefix | Prefix text of the keys in redis | text | none | yes |
| redisUrl | Redis connection url | text | none | yes |
| maxAge | Expire time (Seconds) | number | 24*60*60 | no |
| hash | Function to obtain a hash of each request | function | url of the request | no |
