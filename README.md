# Code Converter

[![Build CodeConverter](https://github.com/icsharpcode/CodeConverter/actions/workflows/dotnet.yml/badge.svg?branch=master&event=push)](https://github.com/icsharpcode/CodeConverter/actions/workflows/dotnet.yml) [![Install](https://vsmarketplacebadge.jeremyrajan.com/api/badge.svg?itemName=SharpDevelopTeam.CodeConverter&install)](https://marketplace.visualstudio.com/items?itemName=SharpDevelopTeam.CodeConverter)

Convert code from VB.NET to C# (and vice versa) using Roslyn - all free and open source:
* [Visual Studio extension](https://marketplace.visualstudio.com/items?itemName=SharpDevelopTeam.CodeConverter)
  * To install close VS and double-click the downloadeded .vsix file
* [Online snippet converter](https://icsharpcode.github.io/CodeConverter/)
* Command line `dotnet tool install ICSharpCode.CodeConverter.codeconv --global` (still requires VS2022 17.1+ installed)
* [Nuget library](https://www.nuget.org/packages/ICSharpCode.CodeConverter/) (this underpins all other free converters you'll find online)

See [wiki](https://github.com/icsharpcode/CodeConverter/wiki) for advice on getting the best results, or the [changelog](https://github.com/icsharpcode/CodeConverter/blob/master/CHANGELOG.md) for recent improvements.

## Visual Studio Extension

Adds context menu items to convert projects/files between VB.NET and C#. See the [wiki documentation](https://github.com/icsharpcode/CodeConverter/wiki) for advice / help using it.

Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=SharpDevelopTeam.CodeConverter) (Use VS 2022 17.1+)

* Flexible: Convert a small selection, or a whole solution in one go, in either direction.
* Accurate: Full project context (through Roslyn) is used to get the most accurate conversion.
* Safe: Conversion runs entirely locally - your code doesn't leave your machine.
* Completely free and open source [GitHub](https://github.com/icsharpcode/CodeConverter#code-converter-) project.
* Integrated: Uses the Output window to show conversion progress / summary.
* Actively developed: User feedback helps us continuously strive for a more accurate conversion.

<p>
<img title="Selected text can be converted" alt="Selected text conversion context menu" src="https://github.com/icsharpcode/CodeConverter/raw/master/.github/img/vbToCsSelection.png" />
</p>

## Contributing

Let us know what needs improving. If you want to get involved in writing the code yourself, even better! We've already had code contributions from several first time GitHub contributors, so don't be shy! See [Contributing.md](https://github.com/icsharpcode/CodeConverter/blob/master/.github/CONTRIBUTING.md) for more info.

The VB -> C# conversion quality is much higher than the C# -> VB conversion quality. The use cases differ considerably as does the supply/demand of improvements.

### Use cases

Visual Basic .NET is slowly dying. It has support for *some* project types on .NET 5, but won't be getting new features according to the [.NET Team Blog](https://devblogs.microsoft.com/vbteam/visual-basic-support-planned-for-net-5-0/). Hence the main use case for:
* VB->C#: moving whole projects
* C#->VB: help incorporate snippets from stack overflow into existing VB codebase, or to help learning one language from the other

## Other ways to use the converter
* Latest CI build (potentially less stable):
  * [See latest build](https://github.com/icsharpcode/CodeConverter/actions/workflows/dotnet.yml?query=is%3Asuccess+branch%3Amaster)
  * Uninstall current version, click on a build and download/install the VSIX file at the bottom of the page
* Integrating the NuGet library
  * See [CodeConversion.ConvertDocumentUnhandledAsync](https://github.com/icsharpcode/CodeConverter/blob/8226313a8d46d5dd73bd35f07af2212e6155d0fd/Vsix/CodeConversion.cs#L226) or [CodeConversion.ConvertProjectUnhandled](https://github.com/icsharpcode/CodeConverter/blob/daa741246770fabf9aa87cd75b753220306aaaaa/Vsix/CodeConversion.cs#L276-L279) in the VSIX project.
  * See [ConverterController](https://github.com/icsharpcode/CodeConverter/blob/master/Web/ConverterController.cs) for a more web-focused API.

## Building/running from source

1. Ensure you have [.NET Core SDK 6.0](https://dotnet.microsoft.com/download/dotnet-core/6.0)
2. Open the solution in Visual Studio 2022+ (Community edition is sufficient)
3. To run the website, set CodeConverter.Web as the startup project
  * You will need [Node (LTS)](https://community.chocolatey.org/packages/nodejs-lts) 16.* (node 17 introduces a breaking change causing ERR_OSSL_EVP_UNSUPPORTED)
5. To run the Visual Studio extension, set Vsix as the startup project
   * A new instance of Visual Studio will open with the extension installed

##  History

A spiritual successor of the code conversion within [SharpDevelop](https://github.com/icsharpcode/SharpDevelop) and later part of [Refactoring Essentials](https://github.com/icsharpcode/RefactoringEssentials), the code converter was separated out to avoid difficulties with different Visual Studio and Roslyn versions.

## More screenshots

<p float="left">
  <img src="https://github.com/icsharpcode/CodeConverter/raw/master/.github/img/solution.png" width="49%" />
  <img src="https://github.com/icsharpcode/CodeConverter/raw/master/.github/img/vbToCsFile.png" width="49%" /> 
  <img src="https://github.com/icsharpcode/CodeConverter/raw/master/.github/img/vbToCsProject.png" width="49%" /> 
  <img src="https://github.com/icsharpcode/CodeConverter/raw/master/.github/img/csToVbProject.png" width="49%" /> 
</p>
