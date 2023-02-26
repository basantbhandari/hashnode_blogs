# GAC in dotnet

In .NET (a software development framework created by Microsoft), GAC stands for Global Assembly Cache. The GAC is a machine-wide cache that stores assemblies (i.e., compiled code libraries) that are intended to be shared by multiple applications on a computer.

When an application needs to use an assembly that is stored in the GAC, it can reference the assembly using its strong name (a unique identifier that includes information about the assembly's version, culture, and public key) instead of specifying the assembly's file path. This allows multiple applications to share the same version of an assembly, and also ensures that the correct version of the assembly is used even if multiple versions are installed on the same computer.

Administrators can use tools like the Global Assembly Cache tool (Gacutil.exe) or Windows PowerShell to manage the GAC, including installing and uninstalling assemblies, viewing assembly information, and resolving assembly dependencies.