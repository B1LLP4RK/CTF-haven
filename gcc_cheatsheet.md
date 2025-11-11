# GCC cheatsheet for reverse engineering

- `help`
  - forms the basis of everything there is to know
  - use `help command` for any command help messages

- `x`
  - must see help file for helpful options with `help x`
  - can use function names with * like `*main+1`
  - continuously press enter to see consecutive memory addresses
  - can access registers with `x $rbp`

- `print`
  - serves different purpose than `x`
  - can see addresses of variables
  - `print $rbp` shows the value ins `$rbp`
    - whereas  `x $rbp` shows the value in memory where `$rbp` points to

- `layout asm`
  - shows assembly code with the CLI
  - if it doesn't show assembly, use `layout prev`, `layout next`
  - use  `C-x a` to toggle between layout mode and cli mode
  - in layout mode, use arrow keys to scroll through assembly code

- `info`
  - shows help messages

- `run`
- `continue`
- `info b`
- `next`
  - executes next line of c code
- `ni`
  - executes next line of assembly code
- `step`
  - step into the function
