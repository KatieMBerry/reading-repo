## JSON Web Tokens
#### https://jwt.io/introduction/
#### https://jwt.io/#debugger-io
- securely transfers info between parties as JSON
- good for passing in HTTP and HTML environments
- easy for client-side to use, especially mobile because smaller
- signed tokens vs encrypted
  - encrypted = hidden
  - signed = verifies inegrity of party using key pairs
  - good for:
     - authorization (ex: single sign-on)
     - info exchange (ex: docusign?)
  - JWT structure: header.payload.signature:
  `` xxxxx.yyyyy.zzzzz ``
  
    - header: includes type of token and signing algorithm (signing algorthims include HMAC SHA256 or RSA)
    ```
    {
      "alg": "HS256",
      "typ": "JWT"
    } 
    ```
    - payload: includes claims
      - registered claims: predefined and recommended (like iss, exp, sub, aud)
      - public claims: should be defined in the IANA JSON Web Token Registry to avoid collision
      - private claims: custom claims agreed to between parties
    ```
    {
      "sub": "1234567890",
      "name": "John Doe",
      "admin": true
    } 
    ```
    - signature: used to verify message wasn't tampered with & can verify sender
     ```
     HMACSHA256(
        base64UrlEncode(header) + "." +
        base64UrlEncode(payload),
        secret)
     ```
     - then all gets encoded and signed with a secret, separated by dots

## BCrypt to hash passwords
#### https://danboterhoven.medium.com/why-you-should-use-bcrypt-to-hash-passwords-af330100b861

- common ways to store passwords that are not very secure:
  - plain text
  - one way hash: hashing algorithm applied to it 
  - salting the password: adds a very long string of bytes to the password (easy to hack if access to source code) 
  - random salt: a random string added for each user, created on the generation of the user account, but still accessible
- BCrypt hashing function
  - Using a Key Factor, adjusts the cost of hashing. With Key Factor changes, the hash output can be influenced
  - resistant to hacks, especially a type of password cracking called rainbow table
  - slows hashing speed significantly, until it’s ultimately no longer a viable strategy
  
## Understanding Bcrypt
#### https://auth0.com/blog/hashing-in-action-understanding-bcrypt/
- scales with computation power and always hashes every password with a salt
- How fast a cryptographic function can calculate a hash has an immediate and significant bearing on how safe the password is
- requires salt by default
- runs in 2 phases:
  1. function ``EksBlowfishSetup`` initializes state of ``eksblowfish`` with cost, salt, and password 
    - runs key schedule, key stretching & key strenghtening: slows down calculations which in turn also slows down attackers
  2. ``OrpheanBeholderScryDoubt`` 192-bit value, encrypted 64 times using ``eksblowfish``
    - output: the cost and the 128-bit salt value concatenated with the result of the encryption loop
- need to consider work factor (cost, ie run the function as slow as possible without affecting UX and w/o needing to use additonal hardware)
