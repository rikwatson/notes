# Building Apps from Powershell for different clients (Whiteboxing)

 * Whiteboxing  
   Having multiple applications build from a single code base where the only difference is the branding

Q: Do we need `devenv` or will `msbuild` do?  
A; Let's hope for `msbuild` - faster, easier to use in a CI environment. It's not like we have big DB or anything.

```bat
rd .\BuildResults /S /Q
md .\BuildResults



REM set msBuildDir=%WINDIR%\Microsoft.NET\Framework\v3.5
set msBuildDir=%WINDIR%\Microsoft.NET\Framework\v4.0.30319
call %msBuildDir%\msbuild.exe  MySolution.sln /p:Configuration=Release /l:FileLogger,Microsoft.Build.Engine;logfile=Manual_MSBuild_ReleaseVersion_LOG.log
set msBuildDir=

XCOPY .\MyProject\Bin\Release\*.* .\BuildResults\ 
```

_c.f._

 * http://stackoverflow.com/questions/5669765/build-visual-studio-project-through-the-command-line
 * https://msdn.microsoft.com/en-us/library/f35ctcxw.aspx
 * http://stackoverflow.com/questions/29839957/projectguid-csproj-how-to-generate-it-correctly - about GUIDs
