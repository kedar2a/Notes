# Idempotency
> The property of certain operations in mathematics and computer science whereby they can be applied multiple times without changing the result beyond the initial application - [wikipedia](https://en.wikipedia.org/wiki/Idempotence)

## [API/Kafka idempotency layer](https://stripe.com/docs/api/idempotent_requests)
- To perform an idempotent request, provide an additional Idempotency-Key: <key> header to the request.
- An idempotency key is a unique value generated by the client which the server uses to recognize subsequent retries of the same request.
- All POST requests accept idempotency keys.
- Servers should recycle/expire keys after 24 hours.
- Saving the resulting status code and body of the first request made for any given idempotency key, regardless of whether it succeeded or failed. Subsequent requests with the same key return the same result, including 500 errors.


## [Designing robust and predictable calls with idempotency](https://stripe.com/blog/idempotency)
- Planning for failure: network, server overload, infra breakdown
- Making liberal use of idempotency: implement server endpoints so that they’re idempotent. Idempotent HTTP semantics around PUT and DELETE
- Guaranteeing “exactly once” semantics:
    + When performing a request, a client generates a unique ID to identify just that operation and sends it up to the server along with the normal payload. The server receives the ID and correlates it with the state of the request on its end. If the client notices a failure, it retries the request with the same ID, and from there it’s up to the server to figure out what to do with it.
    + Consider various network failure cases and handle request accordingly.
- Safely handling failure: exponential backoff 
- Codifying the design of robust APIs: Make sure that failures are handled consistently, safely and responsibly


## Additional Ref:
- https://brandur.org/idempotency-keys
