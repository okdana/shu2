# shu2

**shu2** (*shell-utils version 2*) is a general-purpose utility library for
scripts written with [zsh](http://zsh.sourceforge.net/) 5.3+. It provides
settings and functions commonly needed when writing featureful command-line
tools. Much of the functionality it offers relates to error handling, output
verbosity control, and string manipulation; it also provides 'native' (i.e.,
fast and portable) alternatives to external utilities like `date` and `sleep`.

## Usage

```
# Compile library
% bin/shu2c -q

# Run example script
% ex/hello Alice
Hello, world!
Hello, Alice!
hello: Hello, world!
hello: Hello, Alice!

# Experiment
% bin/shu2 -v shu:io:puts hello world
>>> shu:io:puts hello world
hello world
<<< 0 (267 µs)

% bin/shu2 -v shu:time:strf FMT_RSS
>>> shu:time:strf FMT_RSS
Sat, 13 Jan 2018 02:48:30 -0600
<<< 0 (373 µs)

% bin/shu2 -v shu:time:strf FMT_BOGUS
>>> shu:time:strf FMT_BOGUS
shu2: PANIC in shu:time:strf()! No such time format: SHU_TIME_FMT_BOGUS
shu2: Trace-back (most recent call on top):
  4. shu:time:strf() @ 94
  3. (anon) @ 0
  2. app::main() @ 76
  1. {bin/shu2} @ 156
<<< 199 (703 µs)
```

## Details

Refer to the `doc/` directory for additional information.

## WARNING

This project isn't actually ready for use. The API hasn't been finalised, the
documentation isn't complete, and there's no licence. Right now it is merely a
toy exercise.
