![banner](https://user-images.githubusercontent.com/62464945/193458460-143ec47f-c182-4a76-81d2-0427253c9861.png)

# JSON Web Tokens - in a  nutshell
## What is a JSON Web Token
Let’s say an application has information to transfer securely from its front-end to its backend. This is where a JSON Web Token (JWT) would come in handy.

JWT is an open standard that defines a self-contained way to securely transfer information between two entities, as a JavaScript Object Notation ([JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON)) object. These tokens are signed cryptographically to ensure that their contents have not been altered.
This gives an advantage over sending data in a plain JSON format which would have no way for a client application to verify if its content has not been tampered with, whereas a JSON Web Token, in simple terms, would be an encoded JSON that could be verified by the client application. 

These features allow JWTs to be commonly used as access tokens. Access tokens are what applications use to make API requests on behalf of a user. And they represent the authorization of a specific application to access specific parts of a user’s data since the token can contain information on a user and permissions.

### Structure of a JWT

A JWT is a string that can be split into 3 components:
-	Header
-	Payload
-	Signature

Each component is Base64Url encoded JSON, and they are then joined together with a dot (.) to form a valid JWT.
Here is an example of a valid JWT showing the 3 components:
<img src="https://user-images.githubusercontent.com/62464945/193457773-aa30efef-ec77-4278-bb13-6625f5360639.png" width="800" />

#### JWT Header
This is the first component in a JWT. This section contains information on how the JWT was created and includes the type of token and signing algorithm used. The decoded header content of the example JWT given above would be:
```json
{
  "alg": "HS256",
  "typ": "JWT"
}
```
Where `typ` refers to the token type used, which is JWT and `alg` refers to the singing algorithm used.

#### JWT Payload
This component contains a set of claims which are key-value pairs that are statements of an entity, usually the user. The key states the name of the claim and the value, its value. For example, the claim `"iss": "https://accounts.google.com"` would mean that the `iss`, or its issuer, is `accounts.google.com` .


Each claim can be of three types:
-	**Registered** – A set of useful claims such as `iss` (Issuer), `exp` (Expiration time), `iat` (Issued at). These claims are recommended, but not mandatory and a list of registered claims can be found at [IANA JSON Web Token Registry](https://www.iana.org/assignments/jwt/jwt.xhtml#claims).
-	**Public** – The way these claims are defined is up to the party using the JWT and can also be found at [IANA JSON Web Token Registry](https://www.iana.org/assignments/jwt/jwt.xhtml#claims).
-	**Private** – These are custom claims that are neither registered or public claims and are created to share information between parties. Due to the token being signed, the payload cannot be tampered with. However, this still opens the possibility of the token contents being read and must therefore not contain sensitive information in an unencrypted format.

#### JWT Signature
This is what protects the claims which are the core of the JWT. They can be signed with symmetric or asymmetric keys. And much like a sender signing a letter to allow the receiver to make sure who the sender is through the written signature, the cryptographic signature verifies the JWT’s creator and also verifies that the content has not been tampered with along the way.
This signature is created by taking the encoded header and encoded payload components, a secret and the algorithm mentioned in the header.
