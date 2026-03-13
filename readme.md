Proof of concept for an aioresponses-like library that uses real aiohttp server
related to this discussion: https://github.com/orgs/aio-libs/discussions/45

This is a proof of concept of how a linrary could expose aioresponses-like API
while using real aiohttp server under the hood. It works only with GET requests,
only compare the url, param and method, and only implements assert_called_with.

The breaking changes will be:
- The context manager will be async, as it will need to start the server
- the assert_called_* methods will not work with arbitrary kwargs, instead they will only work with specific args that the request was made with (e.g. url, method, headers, params, etc.)
