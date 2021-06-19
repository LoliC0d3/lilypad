# lilypad
Lilypad is a Node-based website that bypasses popular link redirectors and protectors.

## features
- Completely unlicensed, free code.
- Open JSON API for developers.
- Regularly updated, new redirects are constantly added.
- Easily self-hostable, even compatible with Heroku*.

```* - Hosting on services like Repl and Heroku means certain sites will not work because they are on IPs that are commonly used to bruteforce these services.```

## currently supported
- adshrink.it
- linkvertise (& aliases)
- t.co
- shortly.xyz
- sub2unlock.com / sub2unlock.net
- shortconnect.com
- boost.ink (& aliases)
- adfoc.us
- adf.ly (& aliases)
- ouo.io* / ouo.press*
- ity.im
- won.pe*
- general redirects (tested on bit.ly, tinyurl.com, goo.gl, youtu.be, ow.ly)

[Examples found here](/docs/examples/README.md)

## tba sites
- za.gl
- fc.lc*
- exey.io*

```* - Requires an AntiCaptcha subscription. [Setup information can be found here](/docs/ac-setup/README.md).```

## api endpoints
Here are the current API endpoints for Lilypad.

### GET ``/api/bypass``
The endpoint to get the URL of a tracker/protected link. 

**Parameters**

- ``url`` (required) - base-64 *and* URI encoded URL

```
http://localhost:32333/api/bypass?url=aHR0cHM6Ly90aW55dXJsLmNvbS8zNXVqbmRrZQ==
```

*Example link redirects to [https://github.com/](https://github.com)*.

**Response**

***Successful Run***
```json
{
    "success": true,
    "url": "https://github.com/"
}
```

``success`` tells you if the task succeeded or not.

If ``success`` is ``true``, it will give you a ``url`` variable, linking to the result.

If ``success`` is ``false``, the response will contain an ``err`` object, containing a message, code, and stack - if the error has them.


## special thanks
This was inspired by [Universal Bypass](https://universal-bypass.org/) and some code on the server was adapted from it.

Some code was also used from an attempt of this project a bit farther back - [here](https://github.com/normanlol/bypass-api).

This project is also possible thanks to [AntiCaptcha](http://getcaptchasolution.com/rpsgehhafa) (uses referal link).
