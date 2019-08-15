---
title: HeightMapNode
layout: reference
weight: 0
---
class HeightMapNode
===

| Include: | Terrain/HeightMapNode.h |


[simul::terrain::HeightMapInterface](heightmapinterface.html)

Functions
---

| void | [AddFilter](#AddFilter)(int index, char type) |
| unsigned int | [GetChecksum](#GetChecksum)() |
| unsigned int | [GetColumnChecksum](#GetColumnChecksum)(int col) |
| float  const * | [GetData](#GetData)() |
| simul::terrain::Filter * | [GetFilter](#GetFilter)(int i) |
| simul::terrain::Filter  const * | [GetFilter](#GetFilter)(int i) |
| int | [GetNumFilters](#GetNumFilters)() |
| unsigned int | [GetRowChecksum](#GetRowChecksum)(int row) |
| void | [RemoveFilter](#RemoveFilter)(int index) |
| void | [SetData](#SetData)(float data, int width, int stride) |


Base Classes
---
[simul::terrain::HeightMapInterface](heightmapinterface.html)

Functions
---
<a name="AddFilter"></a>
### void AddFilter(int index, char type)
Add (index=-1 or larger than filter count) or insert a filter that will modify the heightmap.
<a name="GetChecksum"></a>
### unsigned int GetChecksum()
Checksum to say that any part of the heightmap has changed
<a name="GetColumnChecksum"></a>
### unsigned int GetColumnChecksum(int col)
Checksum for what columns have changed
<a name="GetData"></a>
### float  const * GetData()
Get the actual heights in the grid.
<a name="GetFilter"></a>
### simul::terrain::Filter * GetFilter(int i)
Get a pointer to the filter at the index i.
<a name="GetFilter"></a>
### simul::terrain::Filter  const * GetFilter(int i)
Get a pointer to the filter at the index i.
<a name="GetNumFilters"></a>
### int GetNumFilters()
The number of filters.
<a name="GetRowChecksum"></a>
### unsigned int GetRowChecksum(int row)
Checksum for what rows have changed
<a name="RemoveFilter"></a>
### void RemoveFilter(int index)
Remove the specified filter.
<a name="SetData"></a>
### void SetData(float data, int width, int stride)
Set the heights.
