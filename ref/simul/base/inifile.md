---
title: IniFile
layout: reference
weight: 0
---
class IniFile
===

| Include: | Base/inifile.h |



Functions
---

| unsigned int | [AddKeyName](#AddKeyName)(std::string keyname) |
| void | [CaseSensitive](#CaseSensitive)() |
| bool | [DeleteHeaderComment](#DeleteHeaderComment)(unsigned int commentID) |
| void | [DeleteHeaderComments](#DeleteHeaderComments)() |
| bool | [DeleteKey](#DeleteKey)(std::string keyname) |
| bool | [DeleteKeyComment](#DeleteKeyComment)(unsigned int keyID, unsigned int commentID) |
| bool | [DeleteKeyComments](#DeleteKeyComments)(unsigned int keyID) |
| bool | [DeleteValue](#DeleteValue)(std::string keyname, std::string valuename) |
| void | [Erase](#Erase)() |
| long | [FindKey](#FindKey)(std::string keyname) |
| long | [FindValue](#FindValue)(unsigned int keyID, std::string valuename) |
| std::string | [GetValue](#GetValue)(unsigned int keyID, unsigned int valueID, std::string defValue) |
| unsigned int | [GetValueV](#GetValueV)(std::string keyname, std::string valuename, char format, void v1, void v2, void v3, void v4, void v5, void v6, void v7, void v8, void v9, void v10, void v11, void v12, void v13, void v14, void v15, void v16) |
| void | [HeaderComment](#HeaderComment)(std::string comment) |
| std::string | [HeaderComment](#HeaderComment)(unsigned int commentID) |
| bool | [KeyComment](#KeyComment)(unsigned int keyID, std::string comment) |
| std::string | [KeyComment](#KeyComment)(unsigned int keyID, unsigned int commentID) |
| std::string | [KeyName](#KeyName)(unsigned int keyID) |
| unsigned int | [NumHeaderComments](#NumHeaderComments)() |
| unsigned int | [NumKeyComments](#NumKeyComments)(unsigned int keyID) |
| unsigned int | [NumKeys](#NumKeys)() |
| unsigned int | [NumValues](#NumValues)(unsigned int keyID) |
| unsigned int | [NumValues](#NumValues)(std::string keyname) |
| void | [Path](#Path)(std::string newPath) |
| bool | [ReadFile](#ReadFile)() |
| bool | [SetValue](#SetValue)(unsigned int keyID, unsigned int valueID, std::string value) |
| std::string | [ValueName](#ValueName)(unsigned int keyID, unsigned int valueID) |
| bool | [WriteFile](#WriteFile)() |


Functions
---

### <a name="AddKeyName"/>unsigned int AddKeyName(std::string keyname)
Add a key name.

### <a name="CaseSensitive"/>void CaseSensitive()
Sets whether or not keynames and valuenames should be case sensitive.
The default is case insensitive.

### <a name="DeleteHeaderComment"/>bool DeleteHeaderComment(unsigned int commentID)
Delete a header comment.

### <a name="DeleteHeaderComments"/>void DeleteHeaderComments()
Delete all header comments.

### <a name="DeleteKey"/>bool DeleteKey(std::string keyname)
Deletes specified key and all values contained within.
Returns true if key existed and deleted, false otherwise.

### <a name="DeleteKeyComment"/>bool DeleteKeyComment(unsigned int keyID, unsigned int commentID)
Delete a key comment.

### <a name="DeleteKeyComments"/>bool DeleteKeyComments(unsigned int keyID)
Delete all comments for a key.

### <a name="DeleteValue"/>bool DeleteValue(std::string keyname, std::string valuename)
Deletes specified value.
Returns true if value existed and deleted, false otherwise.

### <a name="Erase"/>void Erase()
Deletes all stored ini data.

### <a name="FindKey"/>long FindKey(std::string keyname)
Returns index of specified key, or noID if not found.

### <a name="FindValue"/>long FindValue(unsigned int keyID, std::string valuename)
Returns index of specified value, in the specified key, or noID if not found.

### <a name="GetValue"/>std::string GetValue(unsigned int keyID, unsigned int valueID, std::string defValue)
Gets value of [keyname] valuename =.
Overloaded to return std::string, int, and double.
Returns defValue if key/value not found.

### <a name="GetValueV"/>unsigned int GetValueV(std::string keyname, std::string valuename, char format, void v1, void v2, void v3, void v4, void v5, void v6, void v7, void v8, void v9, void v10, void v11, void v12, void v13, void v14, void v15, void v16)
This is a variable length formatted GetValue routine. All these voids
are required because there is no vsscanf() like there is a vsprintf().
Only a maximum of 8 variable can be read.

### <a name="HeaderComment"/>void HeaderComment(std::string comment)
Add a header comment.

### <a name="HeaderComment"/>std::string HeaderComment(unsigned int commentID)
Return a header comment.

### <a name="KeyComment"/>bool KeyComment(unsigned int keyID, std::string comment)
Add a key comment.

### <a name="KeyComment"/>std::string KeyComment(unsigned int keyID, unsigned int commentID)
Return a key comment.

### <a name="KeyName"/>std::string KeyName(unsigned int keyID)
Returns key names by index.

### <a name="NumHeaderComments"/>unsigned int NumHeaderComments()
Number of header comments.

### <a name="NumKeyComments"/>unsigned int NumKeyComments(unsigned int keyID)
Key comment functions.
Key comments are those comments within a key. Any comments
defined within value names will be added to this list. Therefore,
these comments will be moved to the top of the key definition when
the IniFile::WriteFile() is called.
Number of key comments.

### <a name="NumKeys"/>unsigned int NumKeys()
Returns number of keys currently in the ini.

### <a name="NumValues"/>unsigned int NumValues(unsigned int keyID)
Returns number of values stored for specified key ID.

### <a name="NumValues"/>unsigned int NumValues(std::string keyname)
Returns number of values stored for specified keyname.

### <a name="Path"/>void Path(std::string newPath)
Sets path of ini file to read and write from.

### <a name="ReadFile"/>bool ReadFile()
Reads ini file specified using path.
Returns true if successful, false otherwise.

### <a name="SetValue"/>bool SetValue(unsigned int keyID, unsigned int valueID, std::string value)
Sets value of [keyname] valuename =.
Specify the optional paramter as false (0) if you do not want it to create
the key if it doesn't exist. Returns true if data entered, false otherwise.
Overloaded to accept std::string, int, and double.

### <a name="ValueName"/>std::string ValueName(unsigned int keyID, unsigned int valueID)
Returns value name by index for a given keyname or keyID.

### <a name="WriteFile"/>bool WriteFile()
Writes data stored in class to ini file.

Enums
---
