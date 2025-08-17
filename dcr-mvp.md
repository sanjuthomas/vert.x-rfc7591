## DCR for Client Credential Flow 

### Sample Request 
```
{
  "client_name": "vert.x_is_the_best",
  "grant_types": ["client_credentials"],
  "token_endpoint_auth_method": "client_secret_basic"
}
```

### Sample Response
```
{
  "client_id": "abc123",
  "client_secret": "s3cr3t",
  "client_id_issued_at": 1692297600,
  "client_secret_expires_at": 0
}
```
### Possible values for token_endpoint_auth_method
token_endpoint_auth_method: [client_secret_basic, client_secret_post, client_secret_jwt, private_key_jwt, none]