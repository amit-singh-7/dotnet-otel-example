# Getting Started

Following instructions from:
https://opentelemetry.io/docs/languages/dotnet/getting-started/

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

3. Create dotnet-simple

    ```bash
    mkdir dotnet-simple
    cd dotnet-simple
    dotnet new web
    ```

4. Replace the content of Program.cs with the supplied code.

5. In the Properties subdirectory, replace the content of launchSettings.json with the supplied code.

6. Build and run the application with the following command, then open http://localhost:8080/rolldice in your web browser to ensure it is working.

    ```bash
    dotnet build
    dotnet run
    ```

## Instrumentation

1. Add the packages

    ```bash
    dotnet add package OpenTelemetry.Extensions.Hosting
    dotnet add package OpenTelemetry.Instrumentation.AspNetCore
    dotnet add package OpenTelemetry.Exporter.Console
    ```

2. Replace the builder and the app content of Program.cs with the supplied code.

3. Run your application once again:

    ```bash
    dotnet run
    ```


