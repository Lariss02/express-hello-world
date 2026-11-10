# README

This is the [Express](https://expressjs.com) [Hello world](https://expressjs.com/en/starter/hello-world.html) example

The app in this repo is deployed at Cyclic

## Deployment

Follow the steps below:

Create a new web service with the following values:
  * Build Command: `yarn`
  * Start Command: `node app.js`

That's it! Your web service will be live on your Render URL as soon as the build finishes.

## Error simulation

The `POST /simulate-error` endpoint returns HTTP 500 only when both `ENABLE_ERROR_SIMULATION=true` and `ERROR_SIMULATION_KEY` are configured. Send the configured key in the `x-error-simulation-key` header:

```sh
curl -i -X POST "$BASE_URL/simulate-error" \
  -H "x-error-simulation-key: $ERROR_SIMULATION_KEY"
```

When the endpoint is disabled or the key is invalid, it returns 404. Enable it only for a controlled test window and disable it afterward. The simulated error affects only that request; it does not stop the server.
