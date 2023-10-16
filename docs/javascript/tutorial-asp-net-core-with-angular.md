---
title: "Create an ASP.NET Core app with Angular"
description: In this tutorial, you create an app using ASP.NET Core and Angular
ms.date: 10/16/2023
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: jmartens
ms.technology: vs-javascript
dev_langs:
  - JavaScript
monikerRange: '>= vs-2022'
---
# Tutorial: Create an ASP.NET Core app with Angular in Visual Studio

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]

In this article, you learn how to build an ASP.NET Core project to act as an API backend and an Angular project to act as the UI.

Visual Studio includes ASP.NET Core Single Page Application (SPA) templates that support Angular and React. The templates provide a built-in Client App folder in your ASP.NET Core projects that contains the base files and folders of each framework.

You can use the method described in this article to create ASP.NET Core Single Page Applications that:

- Put the client app in a separate project, outside from the ASP.NET Core project
- Create the client project based on the framework CLI installed on your computer

## Prerequisites

Make sure to install the following:

- Visual Studio 2022 version 17.5 or later with the **ASP.NET and web development** workload installed. Go to the [Visual Studio downloads](https://visualstudio.microsoft.com/downloads/?cid=learn-onpage-download-cta) page to install it for free.
  If you need to install the workload and already have Visual Studio, go to **Tools** > **Get Tools and Features...**, which opens the Visual Studio Installer. Choose the **ASP.NET and web development** workload, then choose **Modify**.
- npm ([https://www.npmjs.com/](https://www.npmjs.com/package/npm)), which is included with Node.js
- Angular CLI ([https://angular.io/cli](https://angular.io/cli))
  This can be the version of your choice

## Create the frontend app

1. In the Start window (choose **File** > **Start Window** to open), select **Create a new project**.

   :::image type="content" source="media/vs-2022/create-new-project.png" alt-text="Screenshot showing Create a new project":::

1. Search for Angular in the search bar at the top and then select **Angular and ASP.NET Core (Preview)**.

   :::image type="content" source="media/vs-2022/angular-choose-template.png" alt-text="Screenshot showing choosing a template":::

1. Name the project **AngularWithASP** and then choose **Create**.

   Solution Explorer shows the following::

   :::image type="content" source="media/vs-2022/asp-net-core-with-angular-solution-explorer.png" alt-text="Screenshot showing Solution Explorer":::

   Compared to the [standalone Angular template](../javascript/tutorial-create-angular-app.md), you see some new and modified files for integration with ASP.NET Core:

   - aspnetcore-https.js
   - proxy.conf.js
   - package.json(modified)
   - angular.json(modified)
   - app.components.ts
   - app.module.ts

## Set the project properties

1. In Solution Explorer, right-click the **AngularWithASP.Server** project and choose **Properties**.

   :::image type="content" source="media/vs-2022/asp-net-core-project-properties-angular.png" alt-text="Screenshot showing Open project properties"::: 

1. In the Properties page, open the **Debug** tab and select **Open debug launch profiles UI** option. Uncheck the **Launch Browser** option for the profile named after the ASP.NET Core project (or https, if present).

   :::image type="content" source="media/vs-2022/asp-net-core-deselect-launch-browser-angular.png" alt-text="Screenshot showing Debug launch profiles UI"::: 

   This prevents opening the web page with the source weather data.

   >[!NOTE]
   > In Visual Studio, *launch.json* stores the startup settings associated with the **Start** button in the Debug toolbar. *launch.json* must be located under the *.vscode* folder.

## Start the project

Press **F5** or select the **Start** button at the top of the window to start the app. Two command prompts appear:

- The ASP.NET Core API project running
- The Angular CLI running the ng start command

>[!NOTE]
> Check console output for messages. For example there might be a message to update Node.js.

The Angular app appears and is populated via the API. If you don't see the app, see [Troubleshooting](#troubleshooting).

## Publish the project

Starting in Visual Studio 2022 version 17.3, you can publish the integrated solution using the Visual Studio Publish tool.

>[!NOTE]
> To use publish, create your JavaScript project using Visual Studio 2022 version 17.3 or later.

1. In Solution Explorer, right-click the **AngularWithASP.Server** project and select **Add** > **Project Reference**.

   The **angularwithasp.client*** project is selected.

1. Choose **OK**.

1. Right-click the ASP.NET Core project again and select **Edit Project File**.

   This opens the *.csproj* file for the project.

   Notice the `<ReferenceOutputAssembly>` has the value set to `false`.

1. In the *.csproj* file, update the project reference and add `<ReferenceOutputAssembly>` with the value set to `false`.

   When you've updated the reference, it should look like the following.

   ```xml
    <ProjectReference Include="..\angularwithasp.client\angularwithasp.client.esproj">
      <ReferenceOutputAssembly>false</ReferenceOutputAssembly>
    </ProjectReference>
   ```

1. Right-click the ASP.NET Core project and choose **Reload Project**.

1. In *Program.cs*, update the check for `Environment.IsDevelopment` so it looks like the following.

   ```csharp
   // Configure the HTTP request pipeline.
   if (app.Environment.IsDevelopment())
   {
      app.UseSwagger();
      app.UseSwaggerUI();
   }
   else
   {
      app.UseDefaultFiles();
      app.UseStaticFiles();
   }
   ```

1. To publish, right click the ASP.NET Core project, choose **Publish**, and select options to match your desired publish scenario, such as Azure, publish to a folder, et al.

   The publish process takes more time than it does for just an ASP.NET Core project, since the `npm run build` command gets invoked when publishing.

   You can modify the `npm run build` command using the **Production Build Command** in the Angular project properties. To modify it, right-click the Angular project in Solution Explorer and choose **Properties**.

## Troubleshooting

### Proxy error

You may see the following error:

```cmd
[HPM] Error occurred while trying to proxy request /weatherforecast from localhost:4200 to https://localhost:5001 (ECONNREFUSED) (https://nodejs.org/api/errors.html#errors_common_system_errors)
```

If you see this issue, most likely the frontend started before the backend. Once you see the backend command prompt up and running, just refresh the Angular App in the browser.

### Verify port

If the weather data does not load correctly, you may also need to verify that your ports are correct.

1. Go to the *launchSettings.json* file in your ASP.NET Core project (in the *Properties* folder). Get the port number from the `applicationUrl` property.

   If there are multiple `applicationUrl` properties, look for one using an `https` endpoint. It should look similar to `https://localhost:7049`.

1. Then, go to the *proxy.conf.js* file for your Angular project (look in the *src* folder). Update the target property to match the `applicationUrl` property in  *launchSettings.json*. When you update it, that value should look similar to this:

   ```js
   target: 'https://localhost:7049',
   ```

## Next steps

For more information about SPA applications in ASP.NET Core, see the Angular section under [Developing Single Page Apps](/aspnet/core/client-side/spa/intro#developing-single-page-apps). The linked article provides additional context for project files such as *aspnetcore-https.js* and *proxy.conf.js*, although details of the implementation are different due to project template differences. For example, instead of a ClientApp folder, the Angular files are contained in a separate project.