# A secure vehicle service reservation application developed using JSP and integrated with the cloud-based IDP, WSO2 Asgardeo.

Here’s a guide to setting up this dynamic web application based on your credentials.

First, update the database credentials in the DBConnection.java file like this:

```java
String dbUrl = "jdbc:mysql:<your db url>";
String dbUser = <database username>;
String dbPassword = <database password>;
```

Next, configure the reservation-app.properties file with the details from your WSO2 Asgardeo console. You can refer to my blog post for more information on setting up these credentials.

```
# The URL of the SAML 2.0 Assertion Consumer
SAML2.AssertionConsumerURL=http://localhost.com:8080/sample-app/home.jsp

# A unique identifier for this SAML 2.0 application
SAML2.SPEntityId=sample-app

# A unique identifier for this SAML 2.0 Identity Provider
SAML2.IdPEntityId=localhost

# The URL of the SAML 2.0 Identity Provider
SAML2.IdPURL=https://localhost:9443/samlsso

# Adanced Properties - Only need to be changed for advanced use cases.

# Url to do send SAML2 SSO AuthnRequest
SAML2SSOURL=samlsso

# URIs to skip SSOAgentFilter; comma separated values
SkipURIs=/sample-app/index.html

IndexPage=index.html

ErrorPage=/error.jsp

# Specify if Single Sign on is enabled/disabled
EnableSAML2SSOLogin=true

# Specify if SingleLogout is enabled/disabled
SAML2.EnableSLO=true

# This is the URL that is used for SLO
SAML2.SLOURL=logout

# Specify if SAMLResponse element is signed
SAML2.EnableResponseSigning=false

# Specify if SAMLAssertion element is signed
SAML2.EnableAssertionSigning=false

# Specify if SAMLAssertion element is encrypted
SAML2.EnableAssertionEncryption=false

# Specify if AuthnRequests and LogoutRequests should be signed
SAML2.EnableRequestSigning=false

# Specify if SAML request is a passive
SAML2.IsPassiveAuthn=false

# Pem content of the IDP public certificate
#IdPPublicCert=<CERTIFICATE_PEM_CONTENT>

# Password of the KeyStore for SAML and OpenID
KeyStorePassword=wso2carbon

# Alias of the IdP's public certificate
IdPPublicCertAlias=wso2carbon

# Alias of the SP's private key
PrivateKeyAlias=wso2carbon

# Private key password to retrieve the private key used to sign AuthnRequest and LogoutRequest messages
PrivateKeyPassword=wso2carbon
```
Ensure you modify the values for SAML2.AssertionConsumerURL, SAML2.SPEntityId, SAML2.IdPEntityId, SAML2.IdPURL, SkipURIs, and IndexPage according to your application credentials from the WSO2 Asgardeo console.

Since this project is built with IntelliJ IDEA, you can run it directly from the IDE. Just make sure to add a Tomcat server in the IDE, deploy the project to the server, and run the project from there.e sure to add Tomcat server to the IDE and add the project to the server. Then you can run the project using the IDE.


