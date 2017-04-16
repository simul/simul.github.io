---
title: FileLoader
layout: reference
---
class simul::base::FileLoader
===
void AcquireFileContents(pointer,bytes,filename_utf8,open_as_text)
------

! Put the file's entire contents into memory, by allocating sufficiently many bytes, and setting the pointer.
! The memory should later be freed by a call to \ref ReleaseFileContents.
! The filename should be unicode UTF8-encoded.
bool FileExists(filename_utf8)
------

! Returns true if and only if the named file exists. If it has a relative path, it is relative to the current directory.
std::string FindFileInPathStack(filename_utf8,path_stack_utf8)
------

! Find the named file relative to one of a given list of paths. Searches from the top of the stack.
int FindIndexInPathStack(filename_utf8,path_stack_utf8)
------

! Find the named file relative to one of a given list of paths, and return the index in the list, -1 if the file was found on the general search path, or -2 if it was not found. Searches from the top of the stack.
double GetFileDate(filename_utf8)
------

! Get the file date as a julian day number. Return zero if the file doesn't exist.
FileLoader GetFileLoader()
------

! Returns a pointer to the current file handler.
void ReleaseFileContents(pointer)
------

! Free the memory allocated by AcquireFileContents.
bool Save(pointer,bytes,filename_utf8,save_as_text)
------

! Save the chunk of memory to storage.
void SetFileLoader(f)
------

! Set the file handling object: call this before any file operations, if at all.
std::string FindFileInPathStack(filename_utf8,path_stack_utf8)
------

! Find the named file relative to one of a given list of paths. Searches from the top of the stack.
int FindIndexInPathStack(filename_utf8,path_stack_utf8)
------

! Find the named file relative to one of a given list of paths, and return the index in the list, -1 if the file was found on the general search path, or path_stack_utf8.size() if it was not found. Searches from the top of the stack.
