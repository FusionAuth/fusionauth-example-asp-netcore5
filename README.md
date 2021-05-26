# Example ASP.NET Core web application

An ASP.NET Core web application using FusionAuth as the identity server.
This application will use an OAuth Authorization Code workflow
and the PKCE extension to log users in. 

PKCE stands for Proof Key for Code Exchange, and is often pronounced "pixie". The feature
is enabled by default by the netcore oauth library.

You need to have dotnetcore installed to run this code. Please note that this application uses netcore 5.0.
If you are using a mac, use this command `brew cask install dotnet-sdk` to setup the development
environment.

Set up FusionAuth as documented in the blog post. 

## Windows install

To deploy and run on Windows, assuming you have the dotnetcore 5.0 runtime installed:

* Open up a terminal (these instructions assume a `cmd` window)
* `cd SampleApp`
* Update `appsettings.json` with the FusionAuth application `ClientId` and the `Authority` as necessary.
* Export the client secret as an environment variable: `set SampleApp__ClientSecret="..."`
* Publish the binary: `dotnet publish -r win-x64`
* Run the application: `bin\Debug\netcoreapp5.0\win-x64\publish\SampleApp.exe`

Visit the local webserver at `http://localhost:5000/` and sign in.

## Mac install

* Open up a terminal (these instructions assume a `cmd` window)
* `cd SampleApp`
* Update `appsettings.json` with the FusionAuth application `ClientId` and the `Authority` as necessary.
* `export SampleApp__ClientSecret="..."`
* `dotnet publish -r osx.10.14-x64`
* `bin/Debug/netcoreapp5.0/osx.10.14-x64/publish/SampleApp`

## Misc

See more deployment options: https://docs.microsoft.com/en-us/dotnet/core/deploying/

See the blog post for more details about setting up FusionAuth: [Securing an ASP.NET Core Razor Pages app with OAuth](https://fusionauth.io/blog/2020/05/06/securing-asp-netcore-razor-pages-app-with-oauth). That blog post was written for dotnet3.1, but the FusionAuth setup should be identical.

We also have [a dotnetcore3.1 example application](https://github.com/FusionAuth/fusionauth-example-asp-netcore).
