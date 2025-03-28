# Compiling-Command-Generator
Used for automated Generation GCC command for compiling C/C++ Projects. This program is suitable for people like me who dont like to use IDE and Cmake for C/C++ development, but instead manually Compile using the original GCC command.  

## Preparation

To use this program, It is necessary to ensure that there is one `ccg_config.json` in the same directory as `CCG.exe` at least.  

You can set arguments for:  
```
"paths": {
    "include" = <stringArray>,
    "lib" = <stringArray>,
    "source_code" = <stringArray>
},
"arguments": {
    "output" = <string>,
    "lib_stuffix" = <string>
}
```
to Facilitate custom compilation command arguments In the `ccg_config.json` File.  

## A Simple Example
The `ccg_config.json` Contains:
```
"paths": {
    "include" = ["./include", "b"],
    "lib" = ["c", "d", "e"],
    "source_code" = ["./src/f.cpp"]
},
"arguments": {
    "output" = "-o Program.exe",
    "lib_stuffix" = "-lstaticlinking"
}
```
After setting the Above arguments, run the `maker.exe` program and you will see that it automatically generates the following GCC compilation command:  
```
g++.exe -fexec-charset=utf-8 -g ./src/f.cpp -I"./include" -I"b" -L"c" -L"d" -L "e" -o Program.exe -lstaticlinking
```