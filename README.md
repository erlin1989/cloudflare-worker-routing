# A simple Cloudflare Worker with built-in routing

One of the downsides of [CloudFlare Workers](https://www.cloudflare.com/products/cloudflare-workers/), is that, unless you're on the Enterprise plan, you're stuck with only one worker script. So, the included routing feature isn't very useful because you can't easily achieve different worker logic for different routes.

Here's a simple CloudFlare Worker with a built-in router that allows you segment your worker logic into different functions and/or "controllers" so you can build something more powerful and with clean separation of concerns while working within the 1 script limit.

Credits to [Dave Willenberg](https://github.com/detroitenglish) and his [Password pwnage CloudFlare Worker](https://github.com/detroitenglish/pw-pwnage-cfworker) for the auto-deploy script and webpack config.

- src/index.js is your main CloudFlare Worker entrypoint. Update the routes in the file and point to your functions / controller.
- src/sample-controller.js contains an example of a basic controller
- src/router.js contains the basic router (feedback welcome)
- src/helpers.js contains some simple response/redirect helper functions
- src/http-method.js is just a simple enum for HTTP verbs.

---

## Quick Start

1. Rename `example.cloudflare.env` to `cloudflare.env` and edit the values as needed.
2. Update the **index.js** file with your routes, use function closures or separate controller files and go to town with a simple CloudFlare Worker with built-in routing!
3. Install deps with `npm install`
4. Launch 🚀 with `npm run deploy`

## Try it live
Try out the following routes from the sample repo live here:
- GET https://anderly.com/cloudflare/
- GET https://anderly.com/cloudflare/12345
- GET https://anderly.com/cloudflare/routes/12345

### License
MIT