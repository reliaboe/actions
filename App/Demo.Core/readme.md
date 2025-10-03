<div align="center">
  <img src="../../aibel_logo_dark.png#gh-dark-mode-only" alt="logo" width="200" height="auto" />
  <img src="../../aibel_logo_light.png#gh-light-mode-only" alt="logo" width="200" height="auto" />
  <h1>Aibel Core Library</h1>
</div>

## Description
This module is a module interface to use for communication over http with the Azure API. This module implements the communication layer between an API and the Azure API.

## How to

### Install

- Install package [Aibel365.Devops.Azure.Http](https://github.com/Aibel365/devops-backend-library-api/pkgs/nuget/Aibel365.Devops.Azure.Http) from package repository.

### Add the module configuration
The module is of a type [IHttpRepositoryModule]([/Aibel365.Devops.Core/Module/Models/AibelHttpModule.cs](https://github.com/Aibel365/devops-backend-library-api/blob/main/Aibel365.Devops.Core/Module/Models/AibelHttpModule.cs)) and therefore needs this module configuration. <strong>Remember to set the Secret and OcpApimSubscriptionKey</strong>. This could be found in the ADP KeyVault and should be registered as part of the Gitops repository for your application. Locally you can put this in the application.local.json. See the core library documentation for environments in .Net.

You can then use <strong>IAzureHttpService</strong> through constructor dependency injection.

```bash
"ApplicationSetting": {
    ...
    "Modules": [
      {
        "Name": "AzureHttpModule",
        "ClientId": "a12c377c-16d8-4ab0-9c87-33e1344d52b5",
        "Scope": "api://04353c76-b16d-410d-b8f6-5604df91635a/.default",
        "Secret": null,
        "Uri": "https://api.apps.aibel.com/azure/v1/",
        "ApiVersion": "v1",
        "OcpApimSubscriptionKey": ""
      },
    ]
  }
```