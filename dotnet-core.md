# .Net Core"

[Home Page](https://www.microsoft.com/net/core), [learn](https://www.microsoft.com/net/learn).

 * [Getting Started](https://docs.microsoft.com/en-us/dotnet/articles/core/getting-started)

[Choosing between .NET core & Framework fro server apps](https://docs.microsoft.com/en-us/dotnet/articles/standard/choosing-core-framework-server)

Install `brew`, then:

```bash
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Install [_.net Core SDK_](https://go.microsoft.com/fwlink/?LinkID=835011)

Initialise some code:

```bash
mkdir hwapp
cd hwapp
dotnet new
```

Run the App

```bash
dotnet restore
dotnet run
```