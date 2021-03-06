# Adobe Identity Management Service APIs

This set of Postman Collections contains commonly used interactions with [Adobe Identity Management Services (IMS) APIs](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/AuthenticationGuide.md);

These Postman Collections have been set up to share the Postman Variable collections generated via __[Adobe I/O Console's Integrations](https://console.adobe.io/integrations) > Export Details to Postman__, which generates a Postman Environment file complete with your Integrations values.

After Exporting the Postman Environment from Adobe I/O Console, ensure you add your Private Key (`-----BEGIN PRIVATE KEY----- ... -----END PRIVATE KEY-----`) to BOTH the Initial and Current values for `PRIVATE_KEY`.


## Obtaining an Access Token to access the Adobe Experience Platform APIs for Non-production Use

The Postman Collection __[Adobe IO Access Token Generation.postman_collection.json](Adobe IO Access Token Generation.postman_collection.json)__ contains two options for generating an Access Token.

Both of these methods are for convenience, and provide a quick way for Developers to obtain an Access Token for non-production use. The reasons these are for non-production user are described in each section.

### Local Signing (Non-production Use Only)

Local signing leverages a 3rd party JSR Assign Crypto library to be loaded and locally sign the JWT Token using the provided Private Key. Using this method the Private Key even leaves the local machine, however 3rd party JavaScript is loaded into the Postman context.

### Remote Signing (Non-production Use Only)

Remote signing sends all parameters required to obtain and access token to an Adobe owned web service (adobeioruntime.net) which generates the Access Token. Using this method the Private Key leaves the local machine and is sent to the Adobe server. While Adobe does no save or persist the Private Key, Adobe recommends never sharing Production Private Keys with _anyone_, including Adobe (much like you should never share your password with anyone!).


