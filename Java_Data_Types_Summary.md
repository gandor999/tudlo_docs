# ☕ Java Data Types (Summary)

Java data types are divided into two main categories:

------------------------------------------------------------------------

## 1. **Primitive Data Types**

Built-in types that hold simple values directly.

  ------------------------------------------------------------------------------
  Type          Size        Example                  Description
  ------------- ----------- ------------------------ ---------------------------
  **byte**      1 byte      `byte b = 10;`           Small integers (-128 to
                                                     127)

  **short**     2 bytes     `short s = 1000;`        Larger integers (-32,768 to
                                                     32,767)

  **int**       4 bytes     `int i = 50000;`         Common integer type

  **long**      8 bytes     `long l = 100000L;`      Very large integers

  **float**     4 bytes     `float f = 3.14f;`       Single-precision decimal

  **double**    8 bytes     `double d = 3.14159;`    Double-precision decimal

  **char**      2 bytes     `char c = 'A';`          Single Unicode character

  **boolean**   1 bit       `boolean flag = true;`   True or false values
  ------------------------------------------------------------------------------

------------------------------------------------------------------------

## 2. **Non-Primitive (Reference) Data Types**

Store **references** to objects, not the actual values.

  -------------------------------------------------------------------------------
  Type             Example                      Description
  ---------------- ---------------------------- ---------------------------------
  **String**       `String name = "Geo";`       Sequence of characters

  **Arrays**       `int[] arr = {1, 2, 3};`     Collection of same-type values

  **Classes**      `Person p = new Person();`   Blueprint for objects

  **Interfaces**   `Runnable r = () -> {};`     Defines methods to implement
  -------------------------------------------------------------------------------

------------------------------------------------------------------------

## 🧩 Summary Table

  ------------------------------------------------------------------------
  Category                   Types              Stored As
  -------------------------- ------------------ --------------------------
  Primitive                  byte, short, int,  Value
                             long, float,       
                             double, char,      
                             boolean            

  Non-Primitive              String, Arrays,    Reference
                             Classes,           
                             Interfaces         
  ------------------------------------------------------------------------

------------------------------------------------------------------------

✅ **Tip:** Primitives are faster and stored on the stack.\
Objects (non-primitives) are stored on the heap.
