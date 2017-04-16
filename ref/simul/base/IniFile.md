---
title: IniFile
layout: reference
---
class simul::base::IniFile
===
unsigned int AddKeyName(keyname)
------

Add a key name.
void CaseInsensitive()
------

void CaseSensitive()
------

Sets whether or not keynames and valuenames should be case sensitive.
The default is case insensitive.
void Clear()
------

bool DeleteHeaderComment(commentID)
------

Delete a header comment.
void DeleteHeaderComments()
------

Delete all header comments.
bool DeleteKey(keyname)
------

Deletes specified key and all values contained within.
Returns true if key existed and deleted, false otherwise.
bool DeleteKeyComment(keyID,commentID)
------

Delete a key comment.
bool DeleteKeyComment(keyname,commentID)
------

bool DeleteKeyComments(keyID)
------

Delete all comments for a key.
bool DeleteKeyComments(keyname)
------

bool DeleteValue(keyname,valuename)
------

Deletes specified value.
Returns true if value existed and deleted, false otherwise.
void Erase()
------

Deletes all stored ini data.
long FindKey(keyname)
------

Returns index of specified key, or noID if not found.
long FindValue(keyID,valuename)
------

Returns index of specified value, in the specified key, or noID if not found.
std::string GetKeyName(keyID)
------

unsigned int GetNumKeys()
------

unsigned int GetNumValues(keyID)
------

unsigned int GetNumValues(keyname)
------

std::string GetValue(keyID,valueID,defValue)
------

Gets value of [keyname] valuename =.
Overloaded to return std::string, int, and double.
Returns defValue if key/value not found.
std::string GetValue(keyname,valuename,defValue)
------

bool GetValueB(keyname,valuename,defValue)
------

double GetValueF(keyname,valuename,defValue)
------

int GetValueI(keyname,valuename,defValue)
------

std::string GetValueName(keyID,valueID)
------

std::string GetValueName(keyname,valueID)
------

unsigned int GetValueV(keyname,valuename,format,v1,v2,v3,v4,v5,v6,v7,v8,v9,v10,v11,v12,v13,v14,v15,v16)
------

This is a variable length formatted GetValue routine. All these voids
are required because there is no vsscanf() like there is a vsprintf().
Only a maximum of 8 variable can be read.
bool HasValue(keyname,valuename)
------

void HeaderComment(comment)
------

Add a header comment.
std::string HeaderComment(commentID)
------

Return a header comment.
bool KeyComment(keyID,comment)
------

Add a key comment.
bool KeyComment(keyname,comment)
------

std::string KeyComment(keyID,commentID)
------

Return a key comment.
std::string KeyComment(keyname,commentID)
------

std::string KeyName(keyID)
------

Returns key names by index.
unsigned int NumHeaderComments()
------

Header comment functions.
Header comments are those comments before the first key.

Number of header comments.
unsigned int NumKeyComments(keyID)
------

Key comment functions.
Key comments are those comments within a key. Any comments
defined within value names will be added to this list. Therefore,
these comments will be moved to the top of the key definition when
the IniFile::WriteFile() is called.

Number of key comments.
unsigned int NumKeyComments(keyname)
------

unsigned int NumKeys()
------

Returns number of keys currently in the ini.
unsigned int NumValues(keyID)
------

Returns number of values stored for specified key.
unsigned int NumValues(keyname)
------

void Path(newPath)
------

Sets path of ini file to read and write from.
std::string Path()
------

bool ReadFile()
------

Reads ini file specified using path.
Returns true if successful, false otherwise.
void Reset()
------

void SetPath(newPath)
------

bool SetValue(keyID,valueID,value)
------

Sets value of [keyname] valuename =.
Specify the optional paramter as false (0) if you do not want it to create
the key if it doesn't exist. Returns true if data entered, false otherwise.
Overloaded to accept std::string, int, and double.
bool SetValue(keyname,valuename,value,create)
------

bool SetValueB(keyname,valuename,value,create)
------

bool SetValueF(keyname,valuename,value,create)
------

bool SetValueI(keyname,valuename,value,create)
------

bool SetValueV(keyname,valuename,format)
------

std::string ValueName(keyID,valueID)
------

Returns value name by index for a given keyname or keyID.
std::string ValueName(keyname,valueID)
------

bool WriteFile()
------

Writes data stored in class to ini file.
