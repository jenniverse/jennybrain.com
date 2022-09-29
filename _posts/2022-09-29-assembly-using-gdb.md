---
title: "Use `gdb` to step through disassembled binary"
toc: true
toc_sticky: true
---

# Assembly using `gdb`

- Start the debugger:

    `gdb [executable_name]`

<br>

- Display assembly code:

    `layout asm`

<br>

- Display registers:

    `layout regs`

<br>

- Set a breakpoint:

    `b [function_name]`

<br>

- Run the code:

    `run [name]`

<br>

- Reload screen:

    `ctrl + l`

<br>

- Move to the next instruction:

    `ni` (pressing ENTER repeats the previous command).

<br>

- Continue:

    `c`

<br>

- Display the function:

    `disas [function_name]`

<br>

- Print value in register in:

    hex: `x/x $[register]`

    decimal: `x/d $[register]`

    string: `x/s $[register]`

<br>

- Print the value in array in decimal:

    `x/[size]wd $[register]`

<br>





