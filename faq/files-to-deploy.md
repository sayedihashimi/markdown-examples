# Why don't all of the files in my project folder get deployed? #

From the **Project** menu select **Package/Publish Settings** to open the **Package/Publish Web** tab of the Project Properties window. A drop-down list in the section labeled **Items to deploy (applies to all deployment methods)** offers three options:

- **Only files needed to run this application**. This is the default value. Visual Studio tries to determine which files are required for the application to run successfully. For example, this includes assemblies in the bin folder, files generated during the build, and files marked as **Content**. To see if a file is marked as **Content**, select the file in **Solution Explorer**, and check the file's Build Action property in the Properties window. You can change the **Build Action** value to **Content** to cause the file to be deployed, or change it to something else, such as **None**, to prevent the file from being deployed. Some file types that are automatically set to **Content** include .master, .svc, .ashx, .asax, .skin, .browser, .config, .and sitemap. A file must be included in the project in order to have a Build Action property.

- **All files in this project**. Visual Studio deploys all files that are included in the project, regardless of their **Build Action** property values.

- **All files in the project folder**. Visual Studio deploys all files that are in the project folder and subfolders, regardless of whether they are included in the project or their **Build Action** property values.

If you are familiar with MSBuild syntax, you can find details about how these three options work in the following files:

- Microsoft.Web.Publishing.OnlyFilesToRunTheApp.targets
- Microsoft.Web.Publishing.AllFilesInTheProject.targets
- Microsoft.Web.Publishing.AllFilesInProjectFolder.targets

These files can be found at the following location in a computer that has Visual Studio installed:

`C:\Program Files (x86)\MSBuild\Microsoft\VisualStudio\v10.0\Web\`