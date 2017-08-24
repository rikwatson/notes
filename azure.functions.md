# Azure Functions

Once I sort this assembly upoad Net4.6 thing out we should be able to have some fun.

See [here](https://docs.microsoft.com/en-us/azure/azure-functions/functions-reference-csharp) for details on this.

Try this [demo](https://blog.serverlessconf.io/get-some-hands-on-time-with-azure-functions-development-for-free-e744f76da000)

Uses C# scripting - what version of C# is this based on?

So, looks like private nuget hosting isn't supported (or is non trivial), just copy the DLL's into the `./bin` folder and `using xxxx;`

 * [Developer's Guide](https://docs.microsoft.com/en-us/azure/azure-functions/functions-reference)
 * [Azure Functions C# script developer reference](https://docs.microsoft.com/en-us/azure/azure-functions/functions-reference-csharp)
 * [Azure Functions: Calling Other Functions](http://devslice.net/2016/09/azure-functions-call-functions/)
 * [Azure Functions & Code Reuse](http://devslice.net/2016/08/azure-functions-reusing-code/)
 * [Use external assemblies and refer csx scripts in Azure Functions](https://integrationforever.wordpress.com/2016/06/14/use-external-assemblies-and-refer-csx-scripts-in-azure-functions/)
 * [How to add assembly references to an Azure Function App](https://blogs.msdn.microsoft.com/benjaminperkins/2017/04/13/how-to-add-assembly-references-to-an-azure-function-app/)