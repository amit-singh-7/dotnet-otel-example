# Instrumentation

Following instructions from:  
https://opentelemetry.io/docs/languages/dotnet/instrumentation/

## Example Application

1. Install .NET SDK from https://dotnet.microsoft.com/en-us/download/dotnet/9.0
   Note: I'm using the MacOS Arm64 installer version.

2. Add dotnet to the PATH

    ```bash
    vi ~/.zshrc
    ```

    add the following line:

    ```bash
    export PATH=$PATH:/usr/local/share/dotnet
    ```

    Save and exit the file.

    ```bash
    source ~/.zshrc
    ```

3. Create dotnet-otel-example

    ```bash
    mkdir dotnet-otel-example
    cd dotnet-otel-example
    dotnet new web
    ```

4. Create the library file named Dice.cs and add the supplied code to it.

5. Create the app file DiceController.cs and add the supplied code to it.

6. Replace the content of the Program.cs file with the supplied code.

7. In the Properties subdirectory, replace the content of launchSettings.json with the supplied code.

8. Run the application

    ```bash
    dotnet run
    ```

9. Test the application by browsing to http://localhost:8080/rolldice?rolls=12

## Instrumentation

1. Install the NuGet packages.

    ```bash
    dotnet add package OpenTelemetry.Exporter.Console
    dotnet add package OpenTelemetry.Extensions.Hosting
    ```

2. Install the AspNetCore Instrumentation Package.

    ```bash
    dotnet add package OpenTelemetry.Instrumentation.AspNetCore
    ```

3. Initialize the SDK

    It is important to configure an instance of the OpenTelemetry SDK as early as possible in your application.

    To initialize the OpenTelemetry SDK for an ASP.NET Core app like in the case of the example app, update the content of the Program.cs file with the supplied code.