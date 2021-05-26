# Example ASP.NET Core web application
An ASP.NET Core web application using FusionAuth as the identity server.

You need to have dotnetcore 5 installed to run this code.

Set up FusionAuth as documented in the blog post. 

To deploy and run on Windows, assuming you have the dotnetcore 5.0 runtime installed:

* Open up a terminal (these instructions assume a `cmd` window)
* `cd SampleApp`
* Update `appsettings.json` with the FusionAuth application `ClientId` and the `Authority` as necessary.
* Export the client secret as an environment variable: `set SampleApp__ClientSecret="..."`
* Publish the binary: `dotnet publish -r win-x64`
* Run the application: `bin\Debug\netcoreapp5.0\win-x64\publish\SampleApp.exe`

Visit the local webserver at `http://localhost:5000/` and sign in.

To run on a macos, use the [scripts here](https://dotnet.microsoft.com/download/dotnet-core/scripts) to install dotnetcore. Do the first 3 steps above.

Then run these commands instead of the last three:
* `cd SampleApp`
* Update `appsettings.json` with the FusionAuth application `ClientId` and the `Authority` as necessary. 
* `export SampleApp__ClientSecret="..."`
* `dotnet publish -r osx.10.14-x64` # or whatever version makes sense
* `bin/Debug/netcoreapp5.0/osx.10.14-x64/publish/SampleApp`

See more deployment options: https://docs.microsoft.com/en-us/dotnet/core/deploying/

See the blog post for more details about setting up FusionAuth: [Securing an ASP.NET Core Razor Pages app with OAuth](https://fusionauth.io/blog/2020/05/06/securing-asp-netcore-razor-pages-app-with-oauth). Note that the blog post was written with netcore3.1 in mind, but the FusionAuth setup won't differ.
