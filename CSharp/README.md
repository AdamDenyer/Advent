# C#
This directory contains C# puzzle solutions in a .NET 10 console application.

## Setup
1. In the `App` directory that contains `App.csproj` create a file called `appsettings.json`
2. Add the following contents to `appsettings.json`
```json
{
    "Current": {
        "Year": "2015",
        "Day": "25",
        "RunAllDays": true
    },
    "Inputs": {
        "Examples": false,
        "Path" : {
            "Windows": "%UserProfile%\\dev\\AdventInputs\\",
            "Linux": "%HOME%/dev/AdventInputs/"
        }
    },
    "OS": "Linux"
}
```
3. Replace the values of the settings as required
    - `Current:Year` must be a year with an existing class and namespace that are referenced in `Program.cs`
    - `Current:Day` must be a date with an existing class that is listed in the current year's class
    - `Current:RunAllDays` determines whether the app just runs the current day, or all days in the current year up to and including the current day
    - `Inputs:Examples` determines whether to use the example input files or the real ones
    - `Inputs:Path:{OS}` must contain the local path to the directory where input files are stored
    - `OS` is the target operating system, and must match one of the names under `Inputs:Path`

## Run
1. Open a terminal in the directory that contains `CSharp.sln`
2. Run .NET commands as usual. For example:
    - `dotnet run --project .\App\` to run the main application
    - `dotnet test` to run all test definitions found within the solution