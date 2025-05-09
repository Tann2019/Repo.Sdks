﻿# R.E.P.O. Modding SDKs and Templates <img src="logo.png" align="right" width="100">
[![GitHub](https://img.shields.io/badge/GitHub-%23121011.svg?logo=github&logoColor=white)](https://github.com/linkoid/Repo.Sdks)
[![Stars](https://img.shields.io/github/stars/linkoid/Repo.Sdks)](https://github.com/linkoid/Repo.Sdks/stargazers)
[![License](https://img.shields.io/github/license/linkoid/Repo.Sdks)](https://github.com/linkoid/Repo.Sdks/tree/main?tab=MIT-1-ov-file)

[![R.E.P.O. Modding](https://custom-icon-badges.demolab.com/badge/R.E.P.O.-Modding-FCD233.svg?labelColor=black&logo=repogame)](https://github.com/zelofi/REPOModdingGuide/wiki)
[![dotnet](https://img.shields.io/badge/dotnet-512BD4?logo=dotnet)](https://dotnet.microsoft.com/en-us/download)
[![MSBuild](https://custom-icon-badges.demolab.com/badge/MSBuild-B35601.svg?logo=msbuild)](https://learn.microsoft.com/en-us/visualstudio/msbuild/msbuild)
[![C#](https://img.shields.io/badge/C%23-239120)](https://dotnet.microsoft.com/en-us/languages/csharp)
[![SmiteUnit](https://custom-icon-badges.demolab.com/badge/SmiteUnit-1F73D5.svg?logo=smiteunit)](https://github.com/linkoid/SmiteUnit)

This monorepo contains source code for multiple SDK and template packages that aids in R.E.P.O. Modding.

| Project                                | Description                                                | Latest Package |
|----------------------------------------|------------------------------------------------------------|:--------------:|
| [Common.Build](/Common.Build)          | Find the local installation of R.E.P.O.                    | [![NuGet](https://img.shields.io/nuget/v/Linkoid.Repo.Common.Build   )](https://www.nuget.org/packages/Linkoid.Repo.Common.Build/    ) | 
| [Plugin.Build](/Plugin.Build)          | Build and run a R.E.P.O. plugin.                           | [![NuGet](https://img.shields.io/nuget/v/Linkoid.Repo.Plugin.Build   )](https://www.nuget.org/packages/Linkoid.Repo.Plugin.Build/    ) | 
| [Plugin.Templates](/Plugin.Templates)  | Templates for R.E.P.O. plugin projects.                    | [![NuGet](https://img.shields.io/nuget/v/Linkoid.Repo.Plugin.Templates)](https://www.nuget.org/packages/Linkoid.Repo.Plugin.Templates/) |
| [Test.Build  ](/Test.Build  )          | Build a test project for a R.E.P.O. plugin.                | [![NuGet](https://img.shields.io/nuget/v/Linkoid.Repo.Test.Build     )](https://www.nuget.org/packages/Linkoid.Repo.Test.Build/      ) | 

## Creating a Plugin with the SDK
There are two ways to the SDK to quickly get started:
* Create a new project using a template.
	* See the [Plugin Templates README](https://github.com/linkoid/Repo.Sdks/tree/main/Plugin.Templates#readme)
* For an existing project, add a package reference to `Linkoid.Repo.Plugin.Build`.
	* See the [Plugin SDK README](https://github.com/linkoid/Repo.Sdks/tree/main/Plugin.Build#readme).

After that, if it hasn't been done already, a `Directory.Repo.props` file should be configured in a folder above all R.E.P.O. solutions/projects.
(e.g. in the User Profile folder.)
An explanation and example can be found in the [Common.Build Readme](https://github.com/linkoid/Repo.Sdks/tree/main/Common.Build#directory-repo-props--targets-files).

## Why Should I use SDKs and Templates?
SDKs and Templates setup a project to include most of the things need for modding in a standardized way with minimal manual setup.
These SDKs are designed to be very flexible and overridable, and to not interfere with other SDKs.
These SDKs also enable others to easily contribute to a codebase without having to uniquily configure every project.
By leveraging the full power of MSBuild, these SDKs will automatically detect the local installation of R.E.P.O.,
and copy the built plugin to the plugins folder automatically, then start the game with the IDE's play button or `dotnet run`.

## The Test Framework
*Work in progress.*

**These templates include everything needed to immediately start writing tests using __SmiteUnit__**.
SmiteUnit will inject unit tests into R.E.P.O. when the plugin initializes, allowing to test more complex
scenarios that weren't possible before. Has a harmony transpiler been throwing lots of errors? Throw that patch in a 
SmiteUnit Test and automate the test process! Did a game update break lots of functions? Run all the tests to see what code needs fixed.
See more details about using SmiteUnit Templates in the Test.Template README: <https://github.com/linkoid/Repo.Sdks/tree/main/Test.Templates#SmiteUnit-Templates>
