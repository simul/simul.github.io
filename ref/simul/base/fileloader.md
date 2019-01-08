---
title: FileLoader
layout: reference
weight: 0
---
class FileLoader
===

| Include: | PlugIns/TrueSkyPluginRender/UnityPluginInterface.h |

An interface to derive from so you can provide your own file load/save functions.
Use SetFileLoader to define the object that Simul will use for file handling.
The default is simul::base::DefaultFileLoader, which uses standard file handling.
  


Functions
---

| void | [AcquireFileContents](#AcquireFileContents)(void pointer, unsigned int bytes, char filename_utf8, bool open_as_text) |
| bool | [FileExists](#FileExists)(char filename_utf8) |
| std::string | [FindFileInPathStack](#FindFileInPathStack)(char filename_utf8, std::vector path_stack_utf8) |
| int | [FindIndexInPathStack](#FindIndexInPathStack)(char filename_utf8, std::vector path_stack_utf8) |
| double | [GetFileDate](#GetFileDate)(char filename_utf8) |
| simul::base::FileLoader * | [GetFileLoader](#GetFileLoader)() |
| void | [ReleaseFileContents](#ReleaseFileContents)(void pointer) |
| bool | [Save](#Save)(void pointer, unsigned int bytes, char filename_utf8, bool save_as_text) |
| void | [SetFileLoader](#SetFileLoader)(simul::base::FileLoader f) |
| std::string | [FindFileInPathStack](#FindFileInPathStack)(char filename_utf8, char path_stack_utf8) |
| int | [FindIndexInPathStack](#FindIndexInPathStack)(char filename_utf8, char path_stack_utf8) |

An interface to derive from so you can provide your own file load/save functions.
Use SetFileLoader to define the object that Simul will use for file handling.
The default is simul::base::DefaultFileLoader, which uses standard file handling.
  


Functions
---

### <a name="AcquireFileContents"/>void AcquireFileContents(void pointer, unsigned int bytes, char filename_utf8, bool open_as_text)
Put the file's entire contents into memory, by allocating sufficiently many bytes, and setting the pointer.
The memory should later be freed by a call to 

### <a name="FileExists"/>bool FileExists(char filename_utf8)
Returns true if and only if the named file exists. If it has a relative path, it is relative to the current directory.

### <a name="FindFileInPathStack"/>std::string FindFileInPathStack(char filename_utf8, std::vector path_stack_utf8)
Find the named file relative to one of a given list of paths. Searches from the top of the stack.

### <a name="FindIndexInPathStack"/>int FindIndexInPathStack(char filename_utf8, std::vector path_stack_utf8)
Find the named file relative to one of a given list of paths, and return the index in the list, -1 if the file was found on the general search path, or -2 if it was not found. Searches from the top of the stack.

### <a name="GetFileDate"/>double GetFileDate(char filename_utf8)
Get the file date as a julian day number. Return zero if the file doesn't exist.

### <a name="GetFileLoader"/>simul::base::FileLoader * GetFileLoader()
Returns a pointer to the current file handler.

### <a name="ReleaseFileContents"/>void ReleaseFileContents(void pointer)
Free the memory allocated by AcquireFileContents.

### <a name="Save"/>bool Save(void pointer, unsigned int bytes, char filename_utf8, bool save_as_text)
Save the chunk of memory to storage.

### <a name="SetFileLoader"/>void SetFileLoader(simul::base::FileLoader f)
Set the file handling object: call this before any file operations, if at all.

### <a name="FindFileInPathStack"/>std::string FindFileInPathStack(char filename_utf8, char path_stack_utf8)
Find the named file relative to one of a given list of paths. Searches from the top of the stack.

### <a name="FindIndexInPathStack"/>int FindIndexInPathStack(char filename_utf8, char path_stack_utf8)
Find the named file relative to one of a given list of paths, and return the index in the list, -1 if the file was found on the general search path, or path_stack_utf8.size() if it was not found. Searches from the top of the stack.
