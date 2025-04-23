# Lode
A design doc for the Lode Programming Language. Maybe real in the future?

## General Syntax
### Variables
Variables are post-type defined:  
```var x : i32 = 5;```

### Types
There are a few base types that are used in Lode:
```
i8, i16, i32, i64, i128, int, fixint
u8, u16, u32, u64, u128, uint, fixuint
f16, f32, f64, f128, f256, float
str, date
```
Most of these are self explanitory, but a couple have some unique features.
#### int, uint, and float
These are arbitrarily-sized numbers, functioning like BigInt/Decimal. However, they will be resized to best fit the current situation if needed. For example, if no number required is bigger than i16, the size of int will be set to the same as i16 at comptime.
#### fixint, fixuint
This is similar to Zig's variable-sized numbers. Their definition is 
```
