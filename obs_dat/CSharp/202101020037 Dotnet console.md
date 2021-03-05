#Csharp 



##### Creating project
```dotnet
dotnet add sln -n "VScodeIntro" //create solution in the same folder
dotnet add sln -o "VscodeIntro" //create solution in folder VscodeIntro
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


##### CLI add references 
```dotnet 
//add dependensy between two independent project
dotnet add [first project name] reference [second project name]

//Example:
dotnet add DataExecurer/DataExecurer.csproj reference DataLib/DataLib.csproj
// add package
dotnet add Test package Newtonsoft.Json //add nuget package to project
//add ref to solution
dotnet sln VScodeIntro.sln add ./IntroUI/IntroUI.csproj
```
##### CLI new
```dotnet
dotnet new [ENTER] //show help
dotnet new console -o myapp //create new console aplication with namespace myapp
dotnet new classlib -n "AnotherLib" //add empty project
dotnet new sln -n "NewSolutionName" //add solution file
```


[dotnet documentation](https://docs.microsoft.com/en-us/dotnet/core/tools/dotnet)


##### Download mysql driver
```dotnet
dotnet add package MySql.Data
```
