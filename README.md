# lilypad
Lilypad is a Node-based website that bypasses popular link redirectors and protectors.

## features
- Completely unlicensed, free code.
- Open JSON API for developers.
- Regularly updated, new redirects are constantly added.
- Easily self-hostable, even compatible with Heroku.

## api endpoints
Here are the current API endpoints for Lilypad.

### GET ``/api/bypass``
The endpoint to get the URL of a tracker/protected link. 

**Parameters**

- ``url`` (required) - base-64 *and* URI encoded URL

```http://localhost:32333/api/bypass?url=aHR0cHM6Ly90aW55dXJsLmNvbS8zNXVqbmRrZQ==```

*Example link used is [https://github.com/](https://github.com)*.

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

If ``success`` is ``false``, the response will contain an ``err`` object, more details below.
