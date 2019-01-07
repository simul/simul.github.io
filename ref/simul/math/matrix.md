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

### <a name="Matrix"/> Matrix(simul::math::Matrix m)
< Default constructor.

### <a name="Matrix"/> Matrix(unsigned int h, unsigned int w, float val)
< Constructor for a matrix of height h and width w.

### <a name="ClearMemory"/>void ClearMemory()
< Reset the matrix to height and width zero.

### <a name="FloatPointer"/>float * FloatPointer(unsigned int row, unsigned int col)
@param [in]       row unsigned     The row.
@param [in]       col unsigned     The column
@return float * Pointer to the values at (row,col)

### <a name="MakeSymmetricFromUpper"/>void MakeSymmetricFromUpper()
< Make a unit matrix.

### <a name="operator()"/>float  & operator()(unsigned int row, unsigned int col)
< Swap rows R1 and R2.

### <a name="Position"/>float * Position(unsigned int row, unsigned int col)
< Default destructor.

### <a name="Resize"/>void Resize(unsigned int h, unsigned int w)
< Reset the matrix and free its buffer memory.
Resize the matrix to height h, width w.

### <a name="Zero"/>void Zero()
Set all values to zero.

### <a name="ZeroEdges"/>void ZeroEdges()
< Constructor for a matrix of height h and width w, filled with value val.

Fields
---

**Width**  < The number of rows.

**V**  < Number of columns.
