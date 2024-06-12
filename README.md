# Let's get started

See [action.yml](action.yml)

```yaml
steps:
- uses: docker://ghcr.io/khulnasoft/crapi-engine:main
  with:
    apiSpecURL: 'https://<my-app-spec-url>'
    apiBasePath: 'https://<my-base-path-url>'
    authUrl: 'https://<my-app-auth-url>'
    authBody: '{"login":"your-username","password":"your-password"}'
    authHeaders:"Authorization: Bearer <AccessToken | APIKEY | SessionHeader | JWT>"
    licenseKey: '<your-license-key>' 
```

**Input Parameter Details:**

1.	**apiSpecURL**: Required
2.	**apiBasePath**: Recommended but optional
3.	**authUrl**: Recommended but optional
4.	**authBody**: Recommended but optional (Either Auth Body or Auth Headers)
5.	**authHeaders**: Recommended but optional (Either Auth Headers or Auth Body)
6.	**licenseKey**: 'your-license-key' (Provided by PerfAI)

**Example (using petstore.io) and Definitions:**

```yaml
apiSpecURL: ' https://petstore.swagger.io/v2/swagger.yaml'
apiBasePath: 'https://petstore.swagger.io/v2'
authUrl: 'https://api.petstore.io/auth/credentials'
authBody: '{"login":"your-username","password":"your-password"}'
authHeaders: '< >'
licenseKey: 'your-license-key'
```


1.	**apiSpecURL**: 'https://petstore.swagger.io/v2/swagger.yaml'
      - This is a URL pointing to the location where the API specification document 
      - (Which is in OpenAPI or Swagger format) can be found.

2.	**apiBasePath**: 'https://petstore.swagger.io/v2'
      - This represents the base path of an API, indicating that all endpoints related to product 
      - Operations would be appended to this base path.

3.	**authUrl**: 'https://api.petstore.io/auth/credentials'
      - This is a URL for the authentication service, where users are redirected to log in and obtain authentication credentials.

4.	**authBody**: '{"login":"your-username","password":"your-password"}'

      - This is a sample JSON object representing the body of an authentication request. 
      - It contains the username and password of the user attempting to authenticate.

5.	**authHeaders**: 'Authorization: Basic <Base64EncodedCredentials>' 

    Sample headers:

      - Bearer token "Authorization: Bearer <AccessToken>" 
      - API Key "Authorization: APIKey <APIKey>"
      - HMAC (Hash-based Message Authentication Code) Authentication "Authorization: HMAC <APIKey>:<Signature>"
      - JSON Web Token (JWT) Authentication "Authorization: Bearer <JWT>"
      - Cookie Header "Cookie: sessionID=abc123; userID=12345"
      - Session Header "Session: 1234567890abcdef"
      - Auth headers can be included in the HTTP request's Authorization header field to authenticate and authorize the client making the API request. The specific header and authentication method used will depend on the API and authentication mechanism being implemented.

6.	**licenseKey**: 'your-license-key'
      - A code or token that allows the user to identify him/herself as a legal customer, and it is optional.

