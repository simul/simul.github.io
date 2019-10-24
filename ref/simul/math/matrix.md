---
title: Matrix
layout: reference
weight: 0
---
class Matrix
===

| Include: | Math/Matrix.h |

A Matrix class.<br>


Functions
---

|  | [Matrix](#Matrix)(simul::math::Matrix m) |
|  | [Matrix](#Matrix)(unsigned int h, unsigned int w, float val) |
| void | [ClearMemory](#ClearMemory)() |
| float * | [FloatPointer](#FloatPointer)(unsigned int row, unsigned int col) |
| void | [MakeSymmetricFromUpper](#MakeSymmetricFromUpper)() |
| float  & | [operator()](#operator())(unsigned int row, unsigned int col) |
| float * | [Position](#Position)(unsigned int row, unsigned int col) |
| void | [Resize](#Resize)(unsigned int h, unsigned int w) |
| void | [Zero](#Zero)() |
| void | [ZeroEdges](#ZeroEdges)() |


The Matrix class can be used for generic matrices of any size. It
has three implementations - one in pure C++, one in Intel assembler for
SSE-capable Pentium III+, and one for PS2.
  


Functions
---
<a name="Matrix"></a>
###  Matrix(simul::math::Matrix m)
< Default constructor.
<a name="Matrix"></a>
###  Matrix(unsigned int h, unsigned int w, float val)
< Constructor for a matrix of height h and width w.
<a name="ClearMemory"></a>
### void ClearMemory()
< Reset the matrix to height and width zero.
<a name="FloatPointer"></a>
### float * FloatPointer(unsigned int row, unsigned int col)
<a name="MakeSymmetricFromUpper"></a>
### void MakeSymmetricFromUpper()
< Make a unit matrix.
<a name="operator()"></a>
### float  & operator()(unsigned int row, unsigned int col)
< Swap rows R1 and R2.
<a name="Position"></a>
### float * Position(unsigned int row, unsigned int col)
< Default destructor.
<a name="Resize"></a>
### void Resize(unsigned int h, unsigned int w)
< Reset the matrix and free its buffer memory.
Resize the matrix to height h, width w.
<a name="Zero"></a>
### void Zero()
Set all values to zero.
<a name="ZeroEdges"></a>
### void ZeroEdges()
< Constructor for a matrix of height h and width w, filled with value val.

Fields
---

**Width**  < The number of rows.

**V**  < Number of columns.
