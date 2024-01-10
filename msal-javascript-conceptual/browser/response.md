---
title: Acquiring and using an access token
description: Learn how to acquire and use an access token
author: EmLauber
manager: CelesteDG

ms.topic: reference
ms.date: 01/10/2024
ms.author: emilylauber
ms.reviewer: dmwendia, cwerner, owenrichards, kengaderdus
---

# Response

MSAL will return an `AuthenticationResult.ts` object as a response to all acquire token APIs:

#### `msal-browser` public APIs for token acquisition:
`loginPopup`, `acquireTokenPopup`, `acquireTokenSilent` or `handleRedirectPromise`

Reference docs for `AuthenticationResult` expanding on each parameter can be found [here](https://azuread.github.io/microsoft-authentication-library-for-js/ref/msal-common/classes/_src_response_authenticationresult_.authenticationresult.html).
