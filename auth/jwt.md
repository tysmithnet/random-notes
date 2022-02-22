# JSON Web Token
20220221134027

#security #jwt #web #authentication #auth #authorization

Method for representing **claims** securely between two parties

## Summary
- open standard
    - RFC 7519
- compact, self-contained
- digitally signed
    - could be HMAC or pub/priv key
        - pub/priv method allows the sender to be guaranteed
    - allows unencrypted JWTs to be verified

## Uses

### Authorization
- user is authenticated and given a token
- future calls will use the token
- SSO uses JWT
- auth can be stateless (no session management) if the token contains all relevant information

### Information exchange
- securely transmit information between services
- pub/priv key
- signature verifies content hasn't changed

## Structure
- 3 parts separated by dots `xxxxx.yyyyy.zzzzz`

### Header
- how should signature be computed?
    - contains token type which is JWT
    - contains signing algorithm

### Payload
- contains claims
- claims are information about the bearer
    - username
    - isadmin
    - email
- 3 types of claims
    - registered
        - predefined claims that are recommended to be interoperable
            - `iss`: issuer
            - `exp`: expiration time
            - `sub`: subject
            - `aud`: audience
            - there are more
    - public
        - typically taken from the [jwt claim registry](https://www.iana.org/assignments/jwt/jwt.xhtml)
    - private
        - known to developers and those the developers want to tell

### Signature
- take the encoded header, encoded payload, and secret and concat them
- HMACSHA256 the whole thing

## Example
- user logs in somehow
- app gives the user JWT
- subsequent requests have the token in the header
    - `Authorization: Bearer the.token.string`
    - header means CORS isn't an issue