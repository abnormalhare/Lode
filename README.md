# Lode
A design doc for the Lode Programming Language. Maybe real in the future?

# General Syntax
## Variables
Variables are post-type defined:  
```var x : i32 = 5;```

## Types
There are a few base types that are used in Lode:
```
i8, i16, i32, i64, i128, int, fixint
u8, u16, u32, u64, u128, uint, fixuint
f16, f32, f64, f128, f256, float
str, date
```
Most of these are self explanitory, but a couple have some unique features.
### int, uint, and float
These are arbitrarily-sized numbers, functioning like BigInt/Decimal. However, they will be resized to best fit the current situation if needed. For example, if no number required is bigger than i16, the size of int will be set to the same as i16 at comptime.
### fixint, fixuint
This is similar to Zig's variable-sized numbers. They are defined like how generics are:  
```var x: fixint(10); // 10-bits```
_Note: Since computers work in powers of 2, In reality their size is only as true as the number they hold. Creating an array of 4 u4's is still going to be 4 bytes wide_

### str
Strings are stored in UTF-8. For ASCII and UTF-16, use `u8[]` and `u16[]` respectively.

### date
This is variable holds the date and time. It holds both the 64-bit unix time as well as the year, month, year week, month week, year day, month day, hour, minute, and second.

## OOP
Lode does not support inheritence. However, it does support a few key things we believe are helpful in procedural programming.

### Traits
