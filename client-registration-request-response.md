## Required Request Attributes 

| Attribute       | Description                               | When Required                                                                   |
| --------------- | ----------------------------------------- | ------------------------------------------------------------------------------- |
| `redirect_uris` | Array of redirection URIs for the client. | **Required** if the client uses `authorization_code` or `implicit` grant types. |


## Optional Request Attributes with Server Defaults (if not provided)

| Attribute          | Default Value                                                                                                                                                                                                                 | Description                                                      |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| `response_types`   | `["code"]`                                                                                                                                                                                                                    | The OAuth 2.0 response types the client will use.                |
| `grant_types`      | Inferred from `response_types`. For example:<br>• `["authorization_code"]` if `response_types=["code"]`.<br>• `["implicit"]` if `response_types=["token"]`.<br>• `["authorization_code", "refresh_token"]` if both supported. | The grant types the client can use.                              |
| `application_type` | `"web"`                                                                                                                                                                                                                       | Indicates whether the client is a `web` or `native` application. |


## Server-Assigned Response Attributes

| Attribute                  | Description                                                                                                        |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `client_id`                | Unique identifier for the client. Required for all subsequent OAuth interactions.                                  |
| `client_secret`            | Shared secret (if applicable, e.g., for `client_secret_*` auth methods). Not always issued (e.g., public clients). |
| `client_id_issued_at`      | Numeric timestamp (seconds since epoch) when the `client_id` was issued.                                           |
| `client_secret_expires_at` | Numeric timestamp for client secret expiration. `0` if it will not expire.                                         |


## Optional Request Attributes 

### Client Metadata

| Attribute     | Description                                                    |
| ------------- | -------------------------------------------------------------- |
| `contacts`    | Array of email addresses of people responsible for the client. |
| `client_name` | Human-readable name of the client.                             |
| `logo_uri`    | URL of the client’s logo.                                      |
| `client_uri`  | Home page of the client.                                       |
| `policy_uri`  | Privacy policy URL.                                            |
| `tos_uri`     | Terms of Service URL.                                          |
