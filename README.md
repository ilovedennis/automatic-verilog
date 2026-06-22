# automatic-verilog

This project is a fork from [HonkW93/automatic-verilog](https://github.com/HonkW93/automatic-verilog).

## Modified Items
1. **Removed `RtlTree`**: The `RtlTree` feature, its related scripts (`rtl.vim`), and commands have been completely removed.
2. **AutoInst Suffix Stripping**: Modified `AutoInst` connection naming so that `_i` and `_o` suffixes on child module ports are automatically stripped from the generated connection signals on the parent/top level (e.g. `.reset_i (reset)` and `.valid_o (valid)`).
3. **AUTOINST with Specific Target File**: Added support for specifying a target module file path directly inside the `/*autoinst*/` comment (e.g. `/*autoinst path/to/module.v */`), and completely removed standard `verilog-library-directories` and `verilog-library-directories-recursive` comment parsing.

## How to Use These Functions

### 1. Basic AutoInst
Place the `/*autoinst*/` comment inside your module instantiation:
```verilog
sub_a u_sub_a (
    /*autoinst*/
);
```
Press `<S-F3>` (or run `:AutoInst`) to populate ports.

### 2. AutoInst with Suffix Stripping
If your sub-module ports end with `_i` or `_o`, the generated connection signals will automatically have the suffixes stripped:
```verilog
// In top-level module:
sub_a u_sub_a (
    /*autoinst*/
        .clk_i                  (clk                            ), //input
        .reset_i                (reset                          ), //input
        .valid_o                (valid                          )  //output
);
```

### 3. AutoInst with a Specific File Path
Include the target module file path within the `/*autoinst*/` comment (supporting absolute paths, relative paths, environment variables, and `~` home directory expansion):
```verilog
sub_a u_sub_a (
    /*autoinst ../rtl/sub_a.v */
);
```
When you run `:AutoInst`, it parses `../rtl/sub_a.v` directly.