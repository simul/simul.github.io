---
title: EnvironmentVariables
layout: reference
---
class simul::base::EnvironmentVariables
===
std::string AppendSimulEnvironmentVariable(name,value)
------

std::string GetExecutableDirectory()
------

! Get the directory where the current exe is held.
std::string GetSimulEnvironmentVariable(name)
------

! Get the named environment variable (Windows only, other platforms return an empty string.
std::string GetWorkingDirectory()
------

! Get the current directory.
std::string SetSimulEnvironmentVariable(name,value)
------

! Set the named environment variable for this process.
void SetWorkingDirectory()
------

! Set the current working directory.
