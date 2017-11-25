# shu2

**shu2** (*shell-utils version 2*) is a general-purpose shell utility library
for scripts written with [zsh](http://zsh.sourceforge.net/) 5.3+. It provides
settings and functions commonly needed when writing featureful command-line
tools. Much of the functionality it offers relates to error handling, output
verbosity control, and string manipulation; it also provides 'native' (i.e.,
fast and portable) alternatives to external utilities like `date` and `sleep`.

## Usage

```
# Compile library
% bin/shuc -q

# Run example script
% ex/hello Alice
Hello, world!
Hello, Alice!
hello: Hello, world!
hello: Hello, Alice!

# Experiment
% bin/shu-repl
Enter commands to evaluate. Press ^C or ^D to exit.

>>> shu::puts hello world
hello world
<<< 0 (143 µs)

>>> shu:time:strf FMT_RSS
Sat, 25 Nov 2017 16:27:15 -0600
<<< 0 (548 µs)
```

## WARNING

This project isn't actually ready for use. The API hasn't been finalised, the
documentation isn't complete, and there's no licence. Right now it is merely a
toy exercise.
