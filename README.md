# Survey123 Field Data Plugin

## The Survey123 plugin is now obsolete

![Try the Tabular CSV plugin](https://i.imgflip.com/47f3ro.jpg)

Please use the [Tabular CSV Plugin](https://github.com/AquaticInformatics/tabular-field-data-plugin#tabular-csv-field-data-plugin) instead, which can read CSVs intended for this plugin, plus many more.

## Maintained for archive purposes only

[![Build status](https://ci.appveyor.com/api/projects/status/p7dj87vw06sv8lq3/branch/master?svg=true)](https://ci.appveyor.com/project/SystemsAdministrator/survey123-field-data-plugin/branch/master)

An AQTS field data plugin for AQTS 2018.4-or-newer systems, which can read [Survey123](https://survey123.arcgis.com/) survey results exported to CSV.

## Want to install this plugin?

- Download the latest release of the plugin [here](../../releases/latest)
- Install it using the [FieldVisitPluginTool](https://github.com/AquaticInformatics/aquarius-field-data-framework/tree/master/src/FieldDataPluginTool)

## CSV file format

See the [plugin documentation](./src/Survey123/Readme.md) for CSV format and configuration information.

## Requirements for building the plugin from source

- Requires Visual Studio 2017 (Community Edition is fine)
- .NET 4.7.2 runtime

## Building the plugin

- Load the `src\Survey123.sln` file in Visual Studio and build the `Release` configuration.
- The `src\Survey123\deploy\Release\Survey123.plugin` file can then be installed on your AQTS app server.

## Testing the plugin within Visual Studio

Use the included `PluginTester.exe` tool from the `Aquarius.FieldDataFramework` package to test your plugin logic on the sample files.

1. Open the HydstraGauging project's **Properties** page
2. Select the **Debug** tab
3. Select **Start external program:** as the start action and browse to `"src\packages\Aquarius.FieldDataFramework.18.4.2\tools\PluginTester.exe`
4. Enter the **Command line arguments:** to launch your plugin

```
/Plugin=Survey123.dll /Json=AppendedResults.json /Data=..\..\..\..\data\survey_123_sample.csv
```

The `/Plugin=` argument can be the filename of your plugin assembly, without any folder. The default working directory for a start action is the bin folder containing your plugin.

5. Set a breakpoint in the plugin's `ParseFile()` methods.
6. Select your plugin project in Solution Explorer and select **"Debug | Start new instance"**
7. Now you're debugging your plugin!

See the [PluginTester](https://github.com/AquaticInformatics/aquarius-field-data-framework/tree/master/src/PluginTester) documentation for more details.

## Installation of the plugin

Use the [FieldDataPluginTool](https://github.com/AquaticInformatics/aquarius-field-data-framework/tree/master/src/FieldDataPluginTool) to install the plugin on your AQTS app server.
