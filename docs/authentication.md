# Authentication

The process for authentication differs depending on whether you are accessing a POST or GET route.

## Authenticating POST Requests

Add an `Authentication` field, with your `api-key` as the value to the post body.

Example python code:

```
import requests

url = "http://brighteyeintel.co.uk/api/ip"
body = {
    "Authentication": "yourapikeygoeshere",
    "querylist":["8.8.8.8"]
}

response = requests.post(url, json=body)
```

## Authenticating GET Requests

Add an `Authentication` query parameter to the request URL, with your `api-key` as the value.

Example python code:

```
import requests

url = "http://brighteyeintel.co.uk/api/bssid/00:11:22:AA:BB:CC"
params = {
    "Authentication": "yourapikeygoeshere"
}

response = requests.get(url, params=params)
```
