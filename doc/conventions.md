# shu2 API conventions

This document describes conventions not strictly related to coding style.

## Naming

* All functions MUST be named using the format `shu:<module>:<name>`. (Consumer
  libraries MUST replace `shu` by their own one- to five-letter prefix.)
  `<module>` MUST be one to five letters long and MUST NOT contain
  non-alphabetic characters. `<name>` SHOULD be a terse libc-style name
  containing only alphanumeric characters.

## Error handling

* Functions MUST panic when given illegal input (unsupported options, &c.) or
  when another condition exists that suggests a programming error. Functions
  MUST NOT panic in response to routine run-time errors like missing files.

* Consumer scripts intended for use by end users SHOULD NOT panic when given
  unsupported options or similar.

* Consumer scripts MUST return immediately if the library can't be loaded.

## Function options

* Functions SHOULD use `getopts` for option parsing.

* Lower-case option letters SHOULD be preferred to upper-case ones. When a pair
  of options is provided to enable/disable a certain behaviour, the lower-case
  option MUST be used for the enable function.

* `+`-prefixed option variants have standardised, library-wide meanings; they
  MUST NOT be used for function-specific behaviour. The following `+`-options
  have been standardised:

  * `+a <name>` — Assign result to array `<name>`.
  * `+A <name>` — Assign result to association `<name>`.
  * `+c`        — Forcibly enable ANSI formatting.
  * `+C`        — Forcibly disable ANSI formatting.
  * `+s <name>` — Assign result to scalar `<name>`.
  * `+V <opts>` — Pass verbosity options `<opts>` to another function.

  A `+` variant is automatically accepted by `getopts` for any given spec
  character; unsupported `+` variants must be caught by a `*` `case` clause (or
  something to that effect).

  Since `+`-options and `-`-options share the same spec character, it is not
  possible to have one that accepts an argument and one that does not.

  Select option letters wisely; do not choose a `-`-option if the function could
  conceivably be extended some day with a conflicting `+`-option.
