# Full Node More

## API Key

It's a good practice to use API key to limit the access to your full node's rest endpoints.

### API Key Setup

Please add the following to your `user.conf` by replacing the zeros with your own key (>= 32 characters).
```
alephium.api.api-key = "0000000000000000000000000000000000000000000000000000000000000000"
```
Restart your full node to make this take effect.

### Use API Key

1. Click on the `Authorize` button on the top right of your Swagger UI:
![full-node-api-key-auth0](media/full-node-api-key-auth0.png)

2. Fill in your key in the value box:
![full-node-api-key-auth1](media/full-node-api-key-auth1.png)

Now you could use Swagger UI as if there is no API key.
