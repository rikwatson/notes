# C# Attributes

## [Conditional("TRACE_ON")]

```csharp
#define TRACE_ON
using System;
using System.Diagnostics;

public class Trace
{
    [Conditional("TRACE_ON")]
    public static void Msg(string msg)
    {
        Console.WriteLine(msg);
    }
}

public class ProgramClass
{
    static void Main()
    {
        Trace.Msg("Now in Main...");
        Console.WriteLine("Done.");
    }
}
```

# [Caller...]

```csharp
public sealed class Logger
{
    public void TraceMessage(string message,
                             [CallerMemberName] string memberName = "",
                             [CallerFilePath] string sourceFilePath = "",
                             [CallerLineNumber] int sourceLineNumber = 0)
    {
        Debug.WriteLine("message: " + message);
        Debug.WriteLine("member name: " + memberName);
        Debug.WriteLine("source file path: " + sourceFilePath);
        Debug.WriteLine("source line number: " + sourceLineNumber);
    }
}
```