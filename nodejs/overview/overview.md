---
title: Overview
author: Dickson-Mwendia
---

# Microsoft Authentication Library for Node (MSAL Node)

MSAL Node enables applications to authenticate users using [Azure AD](https://docs.microsoft.com/azure/active-directory/develop/v2-overview) work and school accounts (AAD), Microsoft personal accounts (MSA) and social identity providers like Facebook, Google, LinkedIn, Microsoft accounts, etc. through [Azure AD B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview#identity-providers) service. It also enables your app to get tokens to access [Microsoft Cloud](https://www.microsoft.com/enterprise) services such as [Microsoft Graph](https://graph.microsoft.io).

### Supported OAuth2.0 grant types

The current version supports the following ways of acquiring tokens:

#### Public Client:

- [Authorization Code Grant](https://oauth.net/2/grant-types/authorization-code/) with [PKCE](https://oauth.net/2/pkce/)
- [Device Code Grant](https://oauth.net/2/grant-types/device-code/)
- [Refresh Token Grant](https://oauth.net/2/grant-types/refresh-token/)
- [Silent Flow](https://docs.microsoft.com/azure/active-directory/develop/msal-acquire-cache-tokens#acquiring-tokens-silently-from-the-cache)
- [Username and Password flow](https://docs.microsoft.com/azure/active-directory/develop/msal-authentication-flows#usernamepassword)

#### Confidential Client:

- [Authorization Code Grant](https://oauth.net/2/grant-types/authorization-code/) with a client credential
- [Refresh Token Grant](https://oauth.net/2/grant-types/refresh-token/)
- [Silent Flow](https://docs.microsoft.com/azure/active-directory/develop/msal-acquire-cache-tokens#acquiring-tokens-silently-from-the-cache)
- [Client Credential Grant](https://oauth.net/2/grant-types/client-credentials/)
- [On-behalf-of flow](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-on-behalf-of-flow)
- [Username and Password flow](https://docs.microsoft.com/azure/active-directory/develop/msal-authentication-flows#usernamepassword)

More details on different grant types supported by Microsoft authentication libraries in general can be found in [MSAL authentication flows](https://docs.microsoft.com/azure/active-directory/develop/msal-authentication-flows).

### Supported application scenarios 

MSAL Node supports the following application scenarios:

- Desktop app that calls web APIs
- Web app that calls web APIs
- Web APIs that call web APIs
- Daemon apps

Learn more about the application scenarios that MSAL Node supports in the [scenarios and authentication flows article](https://docs.microsoft.com/azure/active-directory/develop/authentication-flows-app-scenarios).

## Prerequisites

Before using `@azure/msal-node` you will need to register your app in the Azure portal. Follow thee steps in [App registration](https://docs.microsoft.com/graph/auth-register-app-v2) to register your application in the Azure portal.

## Installation

To install MSAL Node using npm, use the following commands: 

```javascript
npm install @azure/msal-node
```

## Usage

### MSAL basics
- [Understand difference in between Public Client and Confidential Clients](https://docs.microsoft.com/azure/active-directory/develop/msal-client-applications)
- [Initialize a Public Client Application](https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-node/docs/initialize-public-client-application.md)
- [Initialize a Confidential Client Application](https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-node/docs/initialize-confidential-client-application.md)
- [Configuration](https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-node/docs/configuration.md)
- [Request](https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-common/docs/request.md)
- [Response](https://github.com/AzureAD/microsoft-authentication-library-for-js/blob/dev/lib/msal-common/docs/Response.md)

## Samples

There are multiple [samples](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples) included in the repository that use MSAL Node to acquire tokens and can be used for testing purposes.
AAD samples:

- [auth-code](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/auth-code): Express app using OAuth2.0 authorization code flow.
- [auth-code-pkce](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/auth-code-pkce): Express app using OAuth2.0 authorization code flow with PKCE.
- [device-code](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/device-code): Command line app using OAuth 2.0 device code flow.
- [refresh-token](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/refresh-token): Command line app using OAuth 2.0 refresh flow.
- [silent-flow](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/silent-flow): Express app using OAuth2.0 authorization code flow to acquire a token and store in the token cache, and silent flow to use tokens in the token cache.
- [client-credentials](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/client-credentials): Daemon app using OAuth 2.0 client credential grant to acquire a token.
- [on-behalf-of](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/on-behalf-of): Web application using OAuth 2.0 auth code flow to acquire a token for a web API. The web API validates the token, and calls Microsoft Graph on behalf of the user who authenticated in the web application.
- [username-password](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/username-password): Web application using OAuth 2.0 resource owner password credentials (ROPC) flow to acquire a token for a web API.
- [ElectronTestApp](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/ElectronTestApp): Electron desktop application using OAuth 2.0 auth code with PKCE flow to acquire a token for a web API such as Microsoft Graph.
- [ExpressTestApp](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/ExpressTestApp): Express.js MVC web application using OAuth 2.0 auth code with PKCE flow to acquire a token for a web API such as Microsoft Graph.
- [Hybrid Spa Sample](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-browser-samples/HybridSample): Sample demonstrating how to use `enableSpaAuthorizationCode` to perform SSO for applications that leverage server-side and client-side authentication using MSAL Browser and MSAL Node.

B2C samples:

- [b2c-user-flows](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/samples/msal-node-samples/b2c-user-flows): Express app using OAuth2.0 authorization code flow.
- [ms-identity-b2c-javascript-nodejs-management](https://github.com/Azure-Samples/ms-identity-b2c-javascript-nodejs-management/tree/main/Chapter2): Command line app using OAuth 2.0 client credentials flow for performing user management operations on an Azure AD / Azure AD B2C tenant

Others:

- [msal-node-extensions](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/extensions/samples/msal-node-extensions): Uses authorization code flow to acquire tokens and the [msal-extensions](https://github.com/AzureAD/microsoft-authentication-library-for-js/tree/dev/extensions/) library to write the MSAL in-memory token cache to disk.

## Build and test

- If you don't have [lerna](https://github.com/lerna/lerna) installed, run `npm install -g lerna`
- Run `lerna bootstrap` from anywhere within `microsoft-authentication-library-for-js.git`.
- Navigate to `microsoft-authentication-library-for-js/lib/msal-common` and run `npm run build`
- Navigate to `microsoft-authentication-library-for-js/lib/msal-node` and run `npm run build`

```javascript
// to link msal-node and msal-common packages
lerna bootstrap

// Change to the msal-node package directory
cd lib/msal-common/

// To run build only for node package
npm run build

// Change to the msal-node package directory
cd lib/msal-node/

// To run build only for node package
npm run build
```

### Local development

Below is a list of commands you will probably find useful:

#### `npm run build:modules:watch`
Runs the project in development/watch mode. Your project will be rebuilt upon changes. TSDX has a special logger for you convenience. Error messages are pretty printed and formatted for compatibility VS Code's Problems tab. The library will be rebuilt if you make edits.

#### `npm run build`
Bundles the package to the `dist` folder.
The package is optimized and bundled with Rollup into multiple formats (CommonJS, UMD, and ES Module).

#### `lerna bootstrap`
If you are running the project in development/watch mode, or have made changes in `msal-common` and need them reflecting across the project, please run `lerna bootstrap` to link all the symbols. Please note that `npm install` will unlink all the code, hence it is advised to run `lerna bootstrap` post installation.

#### `npm run lint`
Runs eslint with Prettier

#### `npm test`, `npm run test:coverage`, `npm run test:watch`
Runs the test watcher (Jest) in an interactive mode.
By default, runs tests related to files changed since the last commit.
Generate code coverage by adding the flag --coverage. No additional setup needed. Jest can collect code coverage information from entire projects, including untested files.

## Reporting security issues 

If you find a security issue with our libraries or services please report it to [secure@microsoft.com](mailto:secure@microsoft.com) with as much detail as possible. Your submission may be eligible for a bounty through the [Microsoft Bounty](http://aka.ms/bugbounty) program. Please do not post security issues to GitHub Issues or any other public site. We will contact you shortly upon receiving the information. We encourage you to get notifications of when security incidents occur by visiting [this page](https://technet.microsoft.com/security/dd252948) and subscribing to Security Advisory Alerts.
