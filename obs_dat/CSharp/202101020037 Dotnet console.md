#Csharp 



##### Creating project
```dotnet
dotnet add sln -n "VScodeIntro" //create solution
dotnet new console [type of project] -n "IntroUI" //create project IntroUI
dotnet new lib -n "IntroLib"
┌ dotnet sln VScodeIntro.sln add ./IntroUI/IntroUI.csproj //add reference on Windows
└ dotnet sln VScodeIntro.sln add **/*.csproj //add reference on bash
dotnet add ./IntroUI/IntroUI.csproj reference IntroLib/IntroLib.csproj
```


##### CLI flags
```dotnet
dotnet --info //get info of installed sdk, current OS, packages
dotnet --version // get version
dotnet --list-runtimes //Prints out a list of the installed .NET runtimes. SDK lists only
dotnet --list-sdk
dotnet --help
```


##### CLI add 
```dotnet 
//add dependensy between two independent project
dotnet add Test [first project name] reference Test2 [second project name]
dotnet add Test package Newtonsoft.Json //add nuget package to project
dotnet add sln add Test [name of project] //add projects to solution
```
##### CLI new
```dotnet
// - create new console aplication with namespace myapp
dotnet new console -o myapp
dotnet new classlib -n "AnotherLib" //add empty project
dotnet new sln -n "NewSolutionName" //add solution file
//go to the project
	cd myapp
//launch in Visual Code 
	code .
	dotnet restore // - second steep delete all references of the project
	dotnet run // run the application

```


[dotnet documentation](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet)


##### Download mysql driver
```dotnet
dotnet add package MySql.Data
```
