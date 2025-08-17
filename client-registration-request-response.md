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

### Cryptographic Keys

| Attribute  | Description                                   |
| ---------- | --------------------------------------------- |
| `jwks_uri` | URL for the client’s JSON Web Key Set (JWKS). |
| `jwks`     | Inline JWKS (instead of a `jwks_uri`).        |

### Subject Identifier & Sector

| Attribute               | Description                                                          |
| ----------------------- | -------------------------------------------------------------------- |
| `sector_identifier_uri` | URL pointing to a file with redirect URIs for pairwise subject type. |
| `subject_type`          | `public` or `pairwise` subject identifiers.                          |


### ID Token & UserInfo Settings

| Attribute                         | Description                                    |
| --------------------------------- | ---------------------------------------------- |
| `id_token_signed_response_alg`    | JWS alg for signing ID tokens (e.g., `RS256`). |
| `id_token_encrypted_response_alg` | JWE alg for encrypting ID tokens.              |
| `id_token_encrypted_response_enc` | JWE content encryption alg for ID tokens.      |
| `userinfo_signed_response_alg`    | JWS alg for signing UserInfo responses.        |
| `userinfo_encrypted_response_alg` | JWE alg for encrypting UserInfo.               |
| `userinfo_encrypted_response_enc` | JWE content encryption alg for UserInfo.       |

### Request Object Settings

| Attribute                       | Description                                     |
| ------------------------------- | ----------------------------------------------- |
| `request_object_signing_alg`    | JWS alg for signed request objects.             |
| `request_object_encryption_alg` | JWE alg for encrypted request objects.          |
| `request_object_encryption_enc` | JWE content encryption alg for request objects. |


### Token Endpoint Authentication

| Attribute                         | Description                                                                                                                                             |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `token_endpoint_auth_method`      | Client authentication method at the token endpoint: <br>`client_secret_basic`, `client_secret_post`, `client_secret_jwt`, `private_key_jwt`, or `none`. |
| `token_endpoint_auth_signing_alg` | JWS alg for signing JWTs when using `client_secret_jwt` or `private_key_jwt`.                                                                           |

### Authentication & Login

| Attribute            | Description                                                  |
| -------------------- | ------------------------------------------------------------ |
| `default_max_age`    | Default max authentication age (seconds).                    |
| `require_auth_time`  | Boolean; whether `auth_time` claim is required in ID Tokens. |
| `default_acr_values` | Array of default Authentication Context Class References.    |
| `initiate_login_uri` | URL the OP can use to initiate login.                        |
| `request_uris`       | Array of request URIs pre-registered for request objects.    |
