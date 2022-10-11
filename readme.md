- The `dune` file tells Dune how you want the code in that directory (and subdirectories) to be compiled.
- The `dune-project` file is needed in the root directory of every source tree that you want to compile with Dune. It tells Dune what version of Dune to use for this project.
- In general, you’ll have a dune file in every subdirectory of the source tree but only one dune-project file at the root.
- When you run `dune build test.exe` Dune will create a directory `_build` and compile our program inside it. That’s one benefit of the build system over directly running the compiler: instead of polluting your source directory with a bunch of generated files, they get cleanly created in a separate directory. Inside `_build` there are many files that get created by Dune. Our executable is buried a couple of levels down:
```bash
$ _build/default/test.exe
Hello world!
```

To build and execute the program in one step, we can simply run:

```bash
dune exec ./test.exe
Hello world!
```
Finally, to clean up all the compiled code we just run:
```bash
dune clean
```
That removes the _build directory, leaving just your source code.
