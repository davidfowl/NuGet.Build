NuGet.Build
===========

This package includes NuGet.targets, which adds functionality to any solution to restore, update and build NuGet packages.  The default behavior is to simply restore all NuGet packages if they are determined to be missing.  This build script will also keep NuGet up to date automatically.  See below instructions for other options.

These instructions assume a basic working knowledge of XML.  All settings are controlled at an individual project level.  To adjust settings, you should edit your project file with any text editor _(not Visual Studio)_.  Under the PropertyGroup tag, you will need to add the below listed tag with the appropriate value.  Note, there will likely be multiple PropertyGroup tags.  Be sure to use the one with the condition that you want, or use the one that has no condition attribute at all of you want the setting to apply for all configurations.

<table>
	<tr><th>Tag Name</th><th>Value</th><th>Function</th></tr>
	<tr><td>RestorePackages</td><td>false</td><td>Disables restoring packages</td></tr>
	<tr><td></td><td>true</td><td>Enables restoring packages</td></tr>
	<tr><td></td><td>update</td><td>Restores and keeps packages up to date</td></tr>
	<tr></tr>
	<tr><td>BuildPackages</td><td>false</td><td>Disables building of packages</td></tr>
	<tr><td></td><td>true</td><td>Enables building of packages (requires nuspec file in project)</td></tr>
</table>

Note:  When using BuildPackages it is a good practice to use variables in your nuspec file for things such as version number.  See the [NuSpec reference] (http://docs.nuget.org/docs/reference/nuspec-reference) for details on this practice.