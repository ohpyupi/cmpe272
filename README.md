# Authentication with Credential Leakage Protection

## Introduction
Traditional password-based authentication is vulnerable to the credential stuffing attacks where hackers get hold of victims' credentials.

In order to mitigate such attacks, the authentication service can check if the credentials are leaked using a 3rd-party API such as [HaveIBeenPwned](https://haveibeenpwned.com/API/v3).

## Requirements
- For every authentication, check if a user's credential is leaked using HaveIBeenPwned API
- If the API returns a response that indicates the user credential is leaked, serve additional challenge authentication such as OTP.
    - if the user solves the OTP, grant access to the service
    - if not, deny the authentication
- If not, grant access to the service

## Technical Designs
### Use Cases
#### Safe Credentials
In case users credentials are safe and not leaked, the traditional password-based authentication will be served.
#### Leaked Credentials
If the credentials are found to be leaked, using HaveIBeenPwned API, the service will give additional challenge, such as OTP challenge, on top of the password authentication.

### Sequence Diagram
<img src="./out/sequence-diagram/Sequence Diagram.png">

### Limitations
- The API HaveIBeenPwned can return false negatives where users credentials are leaked, but the API does not know about that leakage.
- Potential SLA impact due to the 3rd party API call for every authentication
