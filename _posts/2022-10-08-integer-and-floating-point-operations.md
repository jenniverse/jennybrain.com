---
title: "Integer and floating opint operations"
toc: true
toc_sticky: true
---

# Integer Representation and Operation

## Size and range of types
`char - short - int- long

## Overflow
- Unsigned : `x + y < x / x - y > x`
- Signed: `p + p = n / n + n = p`
- When comparing signed with unsigned, signed is changed to unsigned and compared.

## Shift
- logical: shift in 0's
- arithmetic: replicate MSB
- Diving numbers in the 2's complement system causes rounding to the next smallest integer, not towards 0 as desired.

## Biasing in division by shifting
- Add $2^k-1$ if `x < 0` 
- Then shift

## Binary Multiplication
- Multiplying two (n)-bit numbers yields at most a (2n) bit product.
- When signed → must sign extend partial products (out to 2n bits).

## Binary Division
- Dividing two (n)-bit numbers may yield an (n)-bit quotient and (n)-bit remainder.


# Floating Point

## Floating Point, Base 10
$$
1.2345 \cdot 10^{exp}
$$
- Bias = 4
- Stored as 12345[exp] (ex.123459 = 1.2345*10^5)
- **Not associative**

## Fixed Point, Base 2
- Radix point assumed to be in a fixed location for all numbers.
- Floating points allows the radix point to be in a different location for each value.

## Floating Point, Base 2
$$
\pm b.bbb \cdot 2^{\pm exp}
$$
`[sign] b.[frac] * 2^[exp]`

- Normalized FP format: $\pm 1.bbbbbb \cdot 2^{\pm exp}$
- Floating-point numbers are always normalized.
- The 1. is not stored but assumed since we always will store normalized numbers.

## IEEE 754 Floating Point Formats
### Excess-N Exponent Representation
- Instead of 2's complement
- So that comparisons x < y are simple.
### Single Precision (32-bit)
- `float` in C
- 1 sign bit
- 8 exponent bits
    - range of exponent = -126 to +127
    - value = stored - `127`
- 23 fraction bits
- Equivalent decimal range: 7 digits * $10^{\pm 38}$
- s(1) | exp(8) | fraction(23)

### Double Precision (64-bit)
- `double` in C
- 1 sign bit
- 11 exponent bits
    - value = stored - 1023
- 52 fraction bits
- Equivalent decimal range: 16 digits * $10^{\pm 308}$
- s(1) | exp(11) | fraction(52)

## Special Values
- `float` doesn't wrap around like `int`

## Denormalized
- `0 00000001 0000..0 is (1.0) * 2^-126 == 2^-126 (norm)`
- `0 00000000 1000..0 is (0.1) * 2^-126 == 2^-127 (denorm)`
- `0 00000000 0100..0 is (0.01) * 2^-126 == 2^-128 (denorm)`
- Q. What exponent value is used by denormalized 32-bit floating-point numbers? 
    - A: -126

## 12-bit "IEEE Short" Format
- 1 sign bit, 5 exponent bits (excess 15), 6 fraction bits

## Rounding
### Round to Nearest, Half to Even
- `10...0 : round to even`
- `1x...x : round up`
- `0x...x : round down`
### Round towards 0 (chopping)


## Rounding Implementation -check
- Guard bits: bits immediately after LSB of fraction
- Round bit: bit to the right of the guard bits
- Sticky bit: Logical OR of all other bits after Guard & R bits.

## FP Addition/Subtraction
- **Not associative!!!**
- Add similar, small magnitude numbers first

## FP Multiplication/Division
- **Not associative - order matters!!!**
- Doesn't distribute over addition