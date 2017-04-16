---
title: IniFile
layout: reference
---
class simul::base::IniFile
===
unsigned int AddKeyNamekeyname
------

void CaseInsensitive
------

void CaseSensitive
------

void Clear
------

bool DeleteHeaderCommentcommentID
------

void DeleteHeaderComments
------

bool DeleteKeykeyname
------

bool DeleteKeyCommentkeyID,commentID
------

bool DeleteKeyCommentkeyname,commentID
------

bool DeleteKeyCommentskeyID
------

bool DeleteKeyCommentskeyname
------

bool DeleteValuekeyname,valuename
------

void Erase
------

long FindKeykeyname
------

long FindValuekeyID,valuename
------

std::string GetKeyNamekeyID
------

unsigned int GetNumKeys
------

unsigned int GetNumValueskeyID
------

unsigned int GetNumValueskeyname
------

std::string GetValuekeyID,valueID,defValue
------

std::string GetValuekeyname,valuename,defValue
------

bool GetValueBkeyname,valuename,defValue
------

double GetValueFkeyname,valuename,defValue
------

int GetValueIkeyname,valuename,defValue
------

std::string GetValueNamekeyID,valueID
------

std::string GetValueNamekeyname,valueID
------

unsigned int GetValueVkeyname,valuename,format,v1,v2,v3,v4,v5,v6,v7,v8,v9,v10,v11,v12,v13,v14,v15,v16
------

bool HasValuekeyname,valuename
------

void HeaderCommentcomment
------

std::string HeaderCommentcommentID
------

bool KeyCommentkeyID,comment
------

bool KeyCommentkeyname,comment
------

std::string KeyCommentkeyID,commentID
------

std::string KeyCommentkeyname,commentID
------

std::string KeyNamekeyID
------

unsigned int NumHeaderComments
------

unsigned int NumKeyCommentskeyID
------

unsigned int NumKeyCommentskeyname
------

unsigned int NumKeys
------

unsigned int NumValueskeyID
------

unsigned int NumValueskeyname
------

void PathnewPath
------

std::string Path
------

bool ReadFile
------

void Reset
------

void SetPathnewPath
------

bool SetValuekeyID,valueID,value
------

bool SetValuekeyname,valuename,value,create
------

bool SetValueBkeyname,valuename,value,create
------

bool SetValueFkeyname,valuename,value,create
------

bool SetValueIkeyname,valuename,value,create
------

bool SetValueVkeyname,valuename,format
------

std::string ValueNamekeyID,valueID
------

std::string ValueNamekeyname,valueID
------

bool WriteFile
------

