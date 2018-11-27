---
title: CommandLineParams
layout: reference
weight: 0
---
struct CommandLineParams
===

| Include: | Platform/CrossPlatform/CommandLineParams.h |

A simple structure to store the command-line parameters for an executable.
  


Functions
---

| void | [GetCommandLineParams](#GetCommandLineParams)(simul::crossplatform::CommandLineParams commandLineParams, int argCount, char szArgList) |
| void | [GetCommandLineParams](#GetCommandLineParams)(simul::crossplatform::CommandLineParams commandLineParams, int argCount, wchar_t szArgList) |

A simple structure to store the command-line parameters for an executable.
  


Functions
---

### <a name="GetCommandLineParams"/>void GetCommandLineParams(simul::crossplatform::CommandLineParams commandLineParams, int argCount, char szArgList)
Convert the inputs to an executable into a CommandLineParams struct.

### <a name="GetCommandLineParams"/>void GetCommandLineParams(simul::crossplatform::CommandLineParams commandLineParams, int argCount, wchar_t szArgList)
Convert the inputs to an executable into a CommandLineParams struct.
