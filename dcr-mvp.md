## DCR for Client Credential Flow 

### Sample Request 
```
{
  "client_name": "My M2M Service",
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