## Required attributes 

| Attribute       | Description                               | When Required                                                                   |
| --------------- | ----------------------------------------- | ------------------------------------------------------------------------------- |
| `redirect_uris` | Array of redirection URIs for the client. | **Required** if the client uses `authorization_code` or `implicit` grant types. |


## Attributes with Server Defaults (if not provided)

| Attribute          | Default Value                                                                                                                                                                                                                 | Description                                                      |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| `response_types`   | `["code"]`                                                                                                                                                                                                                    | The OAuth 2.0 response types the client will use.                |
| `grant_types`      | Inferred from `response_types`. For example:<br>• `["authorization_code"]` if `response_types=["code"]`.<br>• `["implicit"]` if `response_types=["token"]`.<br>• `["authorization_code", "refresh_token"]` if both supported. | The grant types the client can use.                              |
| `application_type` | `"web"`                                                                                                                                                                                                                       | Indicates whether the client is a `web` or `native` application. |
