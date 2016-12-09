TransformXml tasks for xbuild
==============================

Provides `<TransformXml/>` tasks for xbuild as described here: https://mzabani.wordpress.com/2013/09/24/mono-asp-net-project-deployment-with-web-config-xdt-transformations/.

To use this in your `.csproj`, build the `TransformXml.dll` (`nuget restore` and `xbuild`) and copy it and the `Microsoft.Web.XmlTransform.dll` to the directory where your `.csproj` file resides. Add
```
<UsingTask TaskName="TransformXml" AssemblyFile="TransformXml.dll" Condition="Exists('TransformXml.dll')" />
```
to the `.csproj` file and use `<TransformXml/>` actions as you would with msbuild.
