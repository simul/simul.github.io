---
title: EnvironmentVariables
layout: reference
weight: 0
---
class EnvironmentVariables
===

| Include: | Base/EnvironmentVariables.h |

A class to manage environment variables.
  


Functions
---

| std::string | [GetExecutableDirectory](#GetExecutableDirectory)() |
| std::string | [GetSimulEnvironmentVariable](#GetSimulEnvironmentVariable)(std::string name) |
| std::string | [GetWorkingDirectory](#GetWorkingDirectory)() |
| std::string | [SetSimulEnvironmentVariable](#SetSimulEnvironmentVariable)(std::string name, std::string value) |
| void | [SetWorkingDirectory](#SetWorkingDirectory)(std::string) |

A class to manage environment variables.
  


Functions
---
<a name="GetExecutableDirectory"></a>
### std::string GetExecutableDirectory()
Get the directory where the current exe is held.
<a name="GetSimulEnvironmentVariable"></a>
### std::string GetSimulEnvironmentVariable(std::string name)
Get the named environment variable (Windows only, other platforms return an empty string.
<a name="GetWorkingDirectory"></a>
### std::string GetWorkingDirectory()
Get the current directory.
<a name="SetSimulEnvironmentVariable"></a>
### std::string SetSimulEnvironmentVariable(std::string name, std::string value)
Set the named environment variable for this process.
<a name="SetWorkingDirectory"></a>
### void SetWorkingDirectory(std::string)
Set the current working directory.
