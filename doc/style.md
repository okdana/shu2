# shu2 style guide

This document describes the coding style used by shu2. It is encouraged (but not
required) to use the same style for shu2 consumer libraries and scripts.

## White space

* 2-space soft tabs MUST be used for indentation.

* Spaces MAY be used for intra-line alignment. Hard tabs MUST NOT be used for
  alignment.

* Source files MUST end with an empty line.

* A single empty line SHOULD be used to separate related blocks of code, where
  appropriate. Source files MUST NOT contain more than one consecutive empty
  line.

## Comments

* Library source files MUST include a 'doc block' comment block. These blocks
  MUST begin with two `#` (hashes) on their own line. Every line that is part of
  the block MUST be prefixed by a `#` (hash), even if it is otherwise empty.

* Consumer-script source files SHOULD include a 'help block' comment block. The
  format/syntax of these blocks is described in the source for `shu:meta:help`.

* Both 'doc block' and 'help block' comment blocks SHOULD be followed by an
  empty line.

* All other comments MUST begin with a single `#` (hash) and MUST NOT be
  followed by an empty line.

* Comments MUST be written in sentence case, with a few exceptions as described
  below. Single-sentence comments SHOULD NOT end with a `.` (full stop).

* The `case` clause terminator `;|` MUST be followed by the comment
  `# MATCH AGAIN`. Similarly, the `;&` terminator MUST be followed by the
  comment `# FALL THROUGH`.

## Quoting

* Strings SHOULD NOT be quoted unless they contain white space or other special
  characters.

* Strings MUST be single-quoted rather than double-quoted unless interpolation
  is desired or the string itself contains a single-quote.

* Strings SHOULD be quoted rather than back-slash-escaped.

* Parameter expansions MUST NOT be quoted unless it is necessary to prevent
  possible elision or the result of the expansion is to be concatenated with
  another expansion or a literal.

* Command substitutions MUST be quoted.

## Misc.

* Unqualified `return` MUST be used instead of `return $?`.

* Functions MUST NOT end with `return` unless an explicit return value is to be
  set.

* Parameters MUST be referenced without the `$` operator where-ever allowed in
  numeric contexts — for example, within arithmetic constructs and as the
  argument to `return`.

* `getopts` option spec strings MUST be sorted alphabetically, with upper-case
  letters following lower-case ones.
