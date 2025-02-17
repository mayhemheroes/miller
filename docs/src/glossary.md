<!---  PLEASE DO NOT EDIT DIRECTLY. EDIT THE .md.in FILE PLEASE. --->
<div>
<span class="quicklinks">
Quick links:
&nbsp;
<a class="quicklink" href="../reference-main-flag-list/index.html">Flags</a>
&nbsp;
<a class="quicklink" href="../reference-verbs/index.html">Verbs</a>
&nbsp;
<a class="quicklink" href="../reference-dsl-builtin-functions/index.html">Functions</a>
&nbsp;
<a class="quicklink" href="../glossary/index.html">Glossary</a>
&nbsp;
<a class="quicklink" href="../release-docs/index.html">Release docs</a>
</span>
</div>
# Glossary

## $*

All [key](#key)-[value](#value) pairs in the current [record](#record), as a [map](reference-main-maps.md).

For example, if `myfile.csv` has [header line](#header-line) `a,b,c`, and the
third [line after the header](#data-line) is `7,8,9`, then the third record
processed by Miller will be the ordered list of key-value pairs `a=7`, `b=8`,
`c=9`, and `$*` will be (using JSON formatting) `{"a": 7, "b": 8, "c": 9 }`.

## @*

All [out-of-stream
variables](reference-dsl-variables.md#out-of-stream-variables), as a
[map](reference-main-maps.md).  Synonymous with `all`.

For example, if out-of-stream variables `@count = 3` and `@sum = 55` have been
assigned, then `@*` will be (using JSON formatting) `{"count": 3, "sum": 55}`.

## absent

The [data type](reference-main-data-types.md) obtained from accessing a missing
key, e.g. `$x` when the current [record](#record) has no [field](#field) named `x`.  See the
[null-data page](reference-main-null-data.md).

## all

All [out-of-stream variables](reference-dsl-variables.md#out-of-stream-variables), as a [map](reference-main-maps.md).
Synonymous with `@*`.

## array

A list of [values](reference-main-data-types.md), indexable by integers [starting with 1](#one-up) for the first value.

## auxents

Stands for _auxiliary entry points_. These are effectively separate programs,
but bundled together inside the Miller executable for convenience. For example,
`mlr termcvt` converts from CR-LF to LF format or vice versa. See the
[auxiliary-commands page](reference-main-auxiliary-commands.md) page for more
information.

## begin

A [keyword](#keyword) in the [Miller programming language](miller-programming-language.md)
indicating the start of a begin
[block](#block) within an instance of the [`put`](#put) or [`filter`](#filter)
[verb](reference-verbs.md).  See [begin/end blocks](reference-dsl-control-structures.md#beginend-blocks).

## block

A group of statements between `{` and `}` in the [Miller programming language](miller-programming-language.md),
including [if-statement bodies](#if), [for-loop bodies](#for), [begin-block bodies](#begin),
[end-block bodies](#end), etc.

## bool

A [keyword](#keyword) for
[type declaration](reference-dsl-variables.md#type-declarations-for-local-variables-function-parameter-and-function-return-values),
used for variables taking boolean (true/false) values.

## break

Used for exiting a [for-loop or while-loop](reference-dsl-control-structures.md)
earlier than its top-of-loop continuation expression would have specific.

## BZIP2 / .bz2

A [data-compression format supported by Miller](reference-main-compressed-data.md).
Files compressed using BZIP2 compression normally end in`.bz2`.

## call

A [keyword](#keyword) used for invoking a
[user-defined subroutine](reference-dsl-user-defined-functions.md#user-defined-subroutines).

## colorization

Miller uses configurable colors for some output to the terminal.  See the
[output-colorization page](output-colorization.md) for more information.

## compression

A [technique](https://en.wikipedia.org/wiki/Data_compression) for having disk
files take up less space. See the [compressed-data page](reference-main-compressed-data.md)
for information on how Miller handles this.

## continue

Used for jumping to the next iteration of a [for-loop or while-loop](reference-dsl-control-structures.md)
without executing the remaining loop-body statements on the current iteration.

## CSV

Stands for _comma-separated values_.  A popular
[file format](file-formats.md#csvtsvasvusvetc) for tabular data, which Miller supports.

## Cygwin

A collection of GNU and open-source tools which provide functionality similar
to a Linux distribution on Windows.  Miller can run inside Cygwin, but does not
need to. See [Miller on Windows](miller-on-windows.md).

## data line

Any line after the first ([header](#header)) line of a [CSV](#csv) or
[TSV](#tsv) file.  The header line contains the keys for all records in the
file; data lines contain values to be zipped together with those keys to form
records. See [record](#record).

Note that a data line can contain more [line](#line) in the sense that
it can contain embedded newlines within double quotes: see also
[RFC 4180](https://datatracker.ietf.org/doc/html/rfc4180)
and the [Miller CSV documentation](file-formats.md#csvtsvasvusvetc).

## delimiter

A _delimiter_ is something that goes in between each item in a list of things.
For example, writing an [array](#array) as `[1,2,3,4,5]`, we can say that the
comma character _delimits_ the list items.

More specifically, in terms of Miller [file formats](file-formats.md),
_delimiter_ can be used as a synonym for [_separator_](#separator).

## division

Miller uses [pythonic division](reference-main-arithmetic.md#pythonic-division)
for quotients of integers, with the exception that integer divided by integer
is integer (not float) if the quotient can be represented exactly as an
integer.

## DKVP

Stands for _delimited key-value pairs_.  A Miller-specific [file
format](file-formats.md#dkvp-key-value-pairs), with each line of a file being
of the form `x=1,y=2,z=3`.  For historical reasons, this is Miller's default
format unless [flags](reference-main-flag-list.md) such as `--csv` are
supplied.  You can also make CSV your default format using a [.mlrrc file](customization.md).

## do

A [keyword](#keyword) which is used to indicate the start of a [do-while loop](reference-dsl-control-structures.md)
in the [Miller programming language](miller-programming-language.md).

## DSL

Stands for _domain-specific language_.
The [Miller programming language](miller-programming-language.md) is embedded within
the [put and filter verbs](reference-dsl.md). It's a language with its own syntax
and semantics; the Miller executable does not embed, say, Python or Lua as a
language for put and filter statements. This makes the Miller programming
language an _embedded domain-specific language_, or _domain-specific language_,
or (more briefly) a _DSL_.

## dump

A [keyword](#keyword) in the [Miller programming
language](miller-programming-language.md) which is used for printing variables to the
screen (namely, to [stdout](#stdout)). Largely synonymous with
[`print`](#print), except that `print` with no arguments prints nothing, while
`dump` with no arguments displays all currently defined [out-of-stream
variables](#out-of-stream-variable).

See also [dump statements](reference-dsl-output-statements.md#dump-statements).

## edump

Same as [`dump`](#dump), except it prints to [stderr](#stderr) rather than [stdout](#stdout).

See also [dump statements](reference-dsl-output-statements.md#dump-statements).

## elif

A [keyword](#keyword)  which is used to indicate the else-if-part of an
[if-statement](reference-dsl-control-structures.md) in the [Miller programming
language](miller-programming-language.md).  In [some
languages](reference-dsl-differences.md) this is `elsif` or `else if`; in
Miller's programming language, `elif`.

## else

A [keyword](#keyword) which is used to indicate the else-part of an
[if-statement](reference-dsl-control-structures.md) in the [Miller programming
language](miller-programming-language.md). See also [`elif`](#elif).

## emit, emitf, emitp

Three [keywords](#keyword) in the
[Miller programming language](miller-programming-language.md)
for injecting new records into the [record](#record) [stream](#stream)
using the [put](#put) or [filter](#filter) [verbs](#verb).

See also the [emit-statements section](reference-dsl-output-statements.md#emit-statements).

## empty

Refers to the string with zero characters. For example, in a CSV file with [header line](#header)
`a,b,c` and data `,,` the three fields are empty; with data `1,2,` the first two fields (`a` and `b`)
are not empty and the third field `c` is empty.

## end

A [keyword](#keyword) in the [Miller programming language](miller-programming-language.md)
indicating the start of an end
[block](#block) within an instance of the [`put`](#put) or [`filter`](#filter)
[verb](reference-verbs.md).  See [begin/end blocks](reference-dsl-control-structures.md#beginend-blocks).

## ENV

A
[keyword](#keyword) in the
[Miller programming language](miller-programming-language.md)
for accessing a readable/writable
[map](#map) of [environment variables](https://en.wikipedia.org/wiki/Environment_variable)

## eprint

Same as [`print`](#print), except it prints to [stderr](#stderr) rather than [stdout](#stdout).

## eprintn

Same as [`printn`](#printn), except it prints to [stderr](#stderr) rather than [stdout](#stdout).

## false

A [keyword](#keyword) in the [Miller programming language](miller-programming-language.md) for the
boolean literal; signified by `False` in Python; in some languages (such as C)
signified by the zero integer value.

## field

A single [key](#key)-[value](#value) pair within a [record](#record).

## file format

A [standard way for encoding information within a text file](https://en.wikipedia.org/wiki/File_format).
Examples include [CSV](#csv), [TSV](#tsv), and [JSON](#json). See the
[file-formats page](file-formats.md) for information on which file formats Miller handles.

## FILENAME

A [built-in variable](reference-dsl-variables.md#built-in-variables) in the
[Miller programming language](miller-programming-language.md) referring to the name
of the current file being processed as Miller [streams](#stream) through your data.

See the section on [built-in variables](reference-dsl-variables.md#built-in-variables).

## FILENUM

A [built-in variable](reference-dsl-variables.md#built-in-variables) in the
[Miller programming language](miller-programming-language.md) referring to the [one-up](#one-up)
index of the current file being processed as Miller [streams](#stream) through your data.

See the section on [built-in variables](reference-dsl-variables.md#built-in-variables).

## filter

Along with [put](#put), one of the Miller [verbs](#verb) which use the [Miller
programming language](miller-programming-language.md).

Also, a [keyword](#keyword) which you can use within `put` statements: see the
page on [DSL filter statements](reference-dsl-filter-statements.md).

See the [DSL overview](#reference-dsl).

## flatten

To convert map-valued and/or array-valued fields to something representable in CSV
and other non-JSON [file formats](file-formats.md) -- either by JSON-stringifying
them or by _key spreading_. See the [flatten/unflatten page](flatten-unflatten.md).

See also [unflatten](#unflatten).

## float

A floating-point number as a value in Miller records, and in the [Miller
programming language](miller-programming-language.md). Floats interconvert seamlessly
with [integers](#int) using Miller's [arithmetic rules](reference-main-arithmetic.md),
so usually you only need to think of _numbers_, rather than ints and floats separately.

Also, `float` is a [keyword](#keyword) for [type declaration](
reference-dsl-variables.md#type-declarations-for-local-variables-function-parameter-and-function-return-values).

## FNR

Like [`NR`](#nr) but resets to 1 at the start of each file in the [input
stream](#streaming).  If you have `mlr ... a.csv b.csv` where `a.csv` has 10
records and `b.csv` has 20, then `FNR` will be 10 on the last record of
`a.csv`, then it will have value 1 on the first record of `b.csv`.

See also the [section on built-in variables](reference-dsl-variables.md#built-in-variables.md).

## for

A [keyword](#keyword)  which is used to indicate the start of a [for-loop](reference-dsl-control-structures.md)
in the [Miller programming language](miller-programming-language.md).

## format

See [file format](#file-format).

## func

A [keyword](#keyword) used for defining a
[user-defined functions](reference-dsl-user-defined-functions.md) in the
[Miller programming language](miller-programming-language.md).

## funct

A type declaration used for local variables, function arguments, and function
return values which are (named) [user-defined functions](#udf) or (unnamed) [function literals](#function-literal).

See the [variables page](reference-dsl-variables.md#type-declarations-for-local-variables-function-parameter-and-function-return-values) for examples.

## function

A bit of callable code in the
[Miller programming language](miller-programming-language.md)
which takes zero or more arguments, and optionally returns a value.

See the [page on built-in functions](reference-dsl-builtin-functions.md) to see
functions which are present in Miller.

See the [page on user-defined functions](reference-dsl-user-defined-functions.md) for how
to write your own functions.

## function literal

A function without a name, like `func(a,b) {return a + 2*b + 7}`, assigned to
a local variable or passed to a [higher-order
function](reference-dsl-higher-order-functions.md) like `apply` or `sort`.  See
the [section on function literals](reference-dsl-user-defined-functions.md#function-literals).

## GZIP / .gz

A [data-compression format supported by Miller](reference-main-compressed-data.md).
Files compressed using GZIP compression normally end in `.gz`.

## hashmap

See [map](#map).

## header line

The first line of a [CSV](#csv) or [TSV](#tsv) file. It contains the keys for
all records in the file; subsequent lines contain values to be zipped together
with those keys to form records. See [record](#record).

Note that a header line can contain more [line](#line) in the sense that
it can contain embedded newlines within double quotes: see also
[RFC 4180](https://datatracker.ietf.org/doc/html/rfc4180)
and the [Miller CSV section](file-formats.md#csvtsvasvusvetc).

## heterogeneity

Referring to data where not all records have the same keys, in the same order.  See the
[record-heterogeneity page](record-heterogeneity.md#ragged-data).

## higher-order function

A function which takes another function as an argument, such as
[`select`](reference-dsl-builtin-functions.md#select) or
[`apply`](reference-dsl-builtin-functions.md#apply). See the [page on
higher-order functions](reference-dsl-higher-order-functions.md).

## homogeneity

Referring to data where all records have the same keys, in the same order.  See the
[record-heterogeneity page](record-heterogeneity.md#homogeneousrectangular-data).

## if

A [keyword](#keyword)  which is used to indicate the start of an [if-statement](reference-dsl-control-structures.md)
in the [Miller programming language](miller-programming-language.md).

## IFS

Stands for _input field separator_. See the [separators page](reference-main-separators.md).

## in

A [keyword](#keyword) in the
[Miller programming language](miller-programming-language.md)
for [single-variable for-loops](reference-dsl-control-structures.md#single-variable-for-loops)
and [key-value for-loops](reference-dsl-control-structures.md#key-value-for-loops).

## in-place

Indicates that a file will be modified after processing. Miller's default mode
is to read one or more files (or standard input on a pipe) and to write to
standard output. This normally goes to the terminal, but can be redirected to
another pipe, or an output file -- for example,
`mlr --csv sort myfile.csv` (prints sorted output to the terminal),
`mlr --csv sort myfile.csv | some-other-command`, or
`mlr --csv sort myfile.csv > newfile.csv`.
In all these cases, the original `myfile.csv` is left unmodified.
But using Miller's `-I` flag, we can update the original file: e.g. `mlr -I --csv sort myfile.csv`
won't print the sorted output to the terminal, but rather will write it back to `myfile.csv`.

See also the [section on in-place mode](reference-main-in-place-processing.md).

## int

A 64-bit signed integer as a value in Miller records, and in the [Miller
programming language](miller-programming-language.md). Ints interconvert seamlessly
with [floats](#float) using Miller's [arithmetic
rules](reference-main-arithmetic.md), so usually you only need to think of
_numbers_, rather than ints and floats separately.

Also, `int` is a [keyword](#keyword) for [type declaration](
reference-dsl-variables.md#type-declarations-for-local-variables-function-parameter-and-function-return-values).

## IPS

Stands for _input pair separator_. See the [separators page](reference-main-separators.md).

## IRS

Stands for _input record separator_. See the [separators page](reference-main-separators.md).

## JSON

Stands for [_JavaScript object notation_](https://www.json.org).  A popular
[file format](file-formats.md#json) for tabular data supported by Miller.

## JSON Lines

A [file format](file-formats.md#json-lines) related to
[JSON](https://www.json.org), supported by Miller. Key points are that every
record is an object written on a single line, without need to be wrapped an
outermost list. This format helps people interoperate with non-JSON-aware
tools in the [Unix toolkit](#unix-toolkit) which generally operate on lines.

## key

The string index in a [map](#map). Also, the name of a field in a [record](#record).

## keyword

A reserved name in the
[Miller programming language](miller-programming-language.md)
which you can't use for any other purpose. For example, `if`, `for`, and `while` are keywords;
trying to define a [local variable](#local-variable) `if = 3` will result in a parse error.

## line

A subsequence of a text file in between line-ending symbols such as the special linefeed character.
Tools in the [Unix toolkit](#unix-toolkit) generally operate on lines; Miller is designed to do
that (using the [NIDX format flags](file-formats.md#nidx-index-numbered-toolkit-style)), as well
as non-line-oriented formats such as [CSV, TSV, JSON, and others](file-formats.md).

## local variable

A [variable](#variable) in the [Miller programming language](miller-programming-language.md)
whose extent is limited to the expression in which it appears; contrast
[out-of-stream variables](#out-of-stream-variable) which endure across the
entire [record stream](#streaming). See the
[section on local variables](reference-dsl-variables.md#local-variables).

## manpage / manual page

A form of on-line help which is [common in Unix-like operating
systems](https://en.wikipedia.org/wiki/Man_page), including MacOS and BSD
variants.

If you've [installed Miller](installing-miller.md) using your system's package-install tools
(versus say [building Miller from source](build.md)),
you can probably see Miller's manual page using `man mlr` at a terminal prompt.
Regardless, you can find the same content [within this documentation site](manpage.md).

## map

A data structure in the [Miller programming language](miller-programming-language.md) containing
an ordered sequence of [key](#key)-[value](#value) pairs.
See the [maps page](reference-main-maps.md) for more information.

Note that Miller operates on [records](#records) by treating them as maps.

## .mlrrc

A file you can create, nominally in your home directory, to customize the
default flag-settings used by Miller. For example, while Miller's default file
format is [DKVP](#dkvp), you can make the default format be CSV so that instead
of `mlr --csv sort myfile.csv` you can simply do `mlr sort myfile.csv`.  See
the [customization page](customization.md).

## MSYS2

[MSYS2](https://www.msys2.org/) is a collection of tools and libraries
providing an easy-to-use environment for building, installing and running
native Windows software. Miller on Windows [no longer requires this as of
Miller version 6](miller-on-windows.md).

## M_E

A [built-in variable](reference-dsl-variables.md#built-in-variables) in the
[Miller programming language](miller-programming-language.md) referring to the mathematic
constant [e](https://en.wikipedia.org/wiki/E_(mathematical_constant)). The _M_ is for _math_.

## M_PI

A [built-in variable](reference-dsl-variables.md#built-in-variables) in the
[Miller programming language](miller-programming-language.md) referring to the
mathematic constant
[π](https://en.wikipedia.org/wiki/Pi). The _M_ is for _math_.

## NF

Stands for _number of fields_. A read-only [built-in
variable](reference-dsl-variables.md#built-in-variables) in the [Miller
programming language](miller-programming-language.md) which shows the number of fields
in the current record.

## NIDX

Stands for _numerically indexed_. This is a format directive telling Miller to
process files one line at a time, splitting lines into fields, with the
resulting fields indexed [one-up](#one-up) as in the [Unix
toolkit](#unix-toolkit).

See also the [file-formats page](file-formats.md).

## NR

Stands for _number of records_. Unlike [`NF`](#nf), which counts definitely the
total number of [fields](#field) within the current [record](#record), since
Miller is [streaming](#streaming) the `NR` [built-in
variable](reference-dsl-variables.md#built-in-variables) counts the number of
records _so far_, counting [upward from one](#one-up). So, on the first record
the `NR` variable will have value 1, on the second record the `NR` variable
will have value 2, and so on.

This increments a total count across files, so if you have `mlr ... a.csv b.csv`
where `a.csv` has 10 records and `b.csv` has 20, then `NR` will be 30 on the last
record of `b.csv`.

See also [`FNR`](#fnr).

See also the [section on built-in variables](reference-dsl-variables.md#built-in-variables).

## null

This term is used in various programming languages to indicate the absence of something:
for example, neither `true` nor `false`, but rather _unspecified_ or _no data available here_.
Miller has more than one kind: see the page on [null/empty/absent data](reference-main-null-data.md).

## num

The `num` [keyword](#keyword) is used for [type declaration](
reference-dsl-variables.md#type-declarations-for-local-variables-function-parameter-and-function-return-values)
in the [Miller programming language](miller-programming-language.md). The `num` type
encompasses both [`int`](#int) and [`float`](#float).  Ints and floats
interconvert seamlessly using Miller's [arithmetic
rules](reference-main-arithmetic.md), so usually you only need to think of
_numbers_, rather than ints and floats separately.

## OFS

Stands for _output field separator_. See the [separators page](reference-main-separators.md).

## one-up

A way of indexing [arrays](#array). If `x=["a", "b", "c"]`, then using one-up indexing,
`x[1]` is `"a"`, `x[2]` is `"b"`, and `x[3]` is `"c"`. Miller uses [one-up indexing](#one-up).
Contrast [zero-up indexing](#zero-up).

See also the [arrays page](reference-main-arrays.md), as well as the page on
[differences from other programming languages](reference-dsl-differences.md).

## oosvar

A whimsical shorthand for [out-of-stream variable](#out-of-stream-variable).

## OPS

Stands for _output pair separator_. See the [separators page](reference-main-separators.md).

## ORS

Stands for _output record separator_. See the [separators page](reference-main-separators.md).

## Out-of-stream variable

[Variables](#variable), prefixed with the `@` sigil, which persist their values
across multiple records in the [Miller programming language](miller-programming-language.md).
See [out-of-stream variables](reference-dsl-variables.md#out-of-stream-variables)
for more information.

## PPRINT

A Miller-specific [file format](file-formats.md#pprint-pretty-printed-tabular)
for [key](#key)-[value](#value) pairs, with columns vertically aligned for easy visual scanning.

## print

A [keyword](#keyword) in the [Miller programming language](miller-programming-language.md) for
printing things to the terminal, with final newline printed for you.

See also [`printn`](#printn) which does not insert the final newline.

See also [`emit`](#emit) which inserts new [records](#record) into the [record stream](#stream).

## printn

A [keyword](#keyword) in the [Miller programming language](miller-programming-language.md) for
printing things to the terminal, with no final newline printed for you.

See also [`print`](#print) which does insert the final newline.

## put

Along with [filter](#filter), one of the Miller [verbs](#verb) which
use the [Miller programming language](miller-programming-language.md).

See the [DSL overview](#reference-dsl).

## ragged

Referring to data where not all records have the same number of keys,
particularly in a malformed-CSV context.  See the
[record-heterogeneity page](record-heterogeneity.md#ragged-data).

## record

An ordered list of [key](#key)-[value](#value) pairs.

Miller's fundamental [streaming](#streaming) operation is to read one record at
a time from input file(s) you specify, using some input format; transforming
those records using one or more [verbs](reference-verbs.md) you specify; then
printing them out in some output format.

For [CSV files](file-formats.md#csvtsvasvusvetc), each record gets its keys
from the file's header line, zipped together with values from a given data
line's [data line](#data-line). For example, if `myfile.csv` has header line `a,b,c`, and the
third line after the header is `7,8,9`, then the third record processed by
Miller will be the ordered list of [key](#key)-[value](#value) pairs `a=7`, `b=8`, `c=9`.

For [JSON files](file-formats.md#json), each record is a JSON object which
isn't nested inside another one.

See also the [Miller command structure page](reference-main-overview.md).

## rectangular

Referring to data where all records have the same keys, in the same order. Synonymous
with [homogeneous](#homogeneity).  See the
[record-heterogeneity page](record-heterogeneity.md#homogeneousrectangular-data).

## REPL

Stands for _read-evaluate-print loop_, such as when you invoke `python` with no
arguments: a place where you can type `1+2` and get `3`. Miller has a
[REPL](repl.md) you can use.

## return

A [keyword](#keyword) in the [Miller programming language](miller-programming-language.md) which
is used for returning control from a
[function](reference-dsl-user-defined-functions.md) to its caller, optionally
returning a value from the function.

## semicolon

Semicolons are used to [delimit statements](reference-dsl-syntax.md) in the
[Miller programming language](miller-programming-language.md).

## separator

Used in two senses:

(1) In some programming languages, such as C, C++, and Java, semicolons are
required after every statement; in others such as Python, they're not required
at all; in yet others, they're required _in between_ statements but are
optional after the last. Miller is in the third category, so we can say that
semicolons are _separators_, not [_terminators_](#terminator), within the
[Miller programming language](miller-programming-language.md).

(2) Refers to character sequences which separate records from one another (like
newlines, sometimes), fields from one another (like commas in CSV), and keys
from values in key-value pairs (`=` or `:`, perhaps).  See the [separators
page](reference-main-separators.md) for more information.

## sparse

Referring to data where not all records have the same keys.  See the
[record-heterogeneity
page](record-heterogeneity.md#sparse-data).

## stderr

A [keyword](#keyword) in the
[Miller programming language](miller-programming-language.md)
for [print, dump, and tee statements](reference-dsl-output-statements.md#tee-statements)
indicating that data are to be sent to the
[_standard error_](https://en.wikipedia.org/wiki/Standard_streams#Standard_error_(stderr)).

## stdout

A [keyword](#keyword) in the
[Miller programming language](miller-programming-language.md)
for [print, dump, and tee statements](reference-dsl-output-statements.md#tee-statements)
indicating that data are to be sent to the
[_standard output_](https://en.wikipedia.org/wiki/Standard_streams#Standard_output_(stdout)).

## str

A [keyword](#keyword) for
[type declaration](reference-dsl-variables.md#type-declarations-for-local-variables-function-parameter-and-function-return-values),
indicating that a variable is intended to be of type
[string](reference-main-data-types.md).

## streaming

Refers to operations which can be done a record at a time, so (a) output is
produced as input records arrive, before end of input stream, and (b) memory
usage is typically bounded.  The latter means that a streaming processor can
operate on data files larger than system memory.  Most of Miller's operations
are streaming; some (such as `sort`) need to see all data before producing any
output, and are non-streaming. Please see the page on [Streaming processing and
memory usage](streaming-and-memory.md).

## subr

A [keyword](#keyword) used for defining a
[user-defined subroutine](reference-dsl-user-defined-functions.md#user-defined-subroutines).

## subroutine

A [user-definable bit of code](reference-dsl-user-defined-functions.md) in the
[Miller programming language](miller-programming-language.md), intended to be
called for its side effects rather than for returning a value.

## tee

In Unix-like and other systems, a
[tee](https://en.wikipedia.org/wiki/Tee_(command)) is a command which reads
standard input and writes both standard output and a specified file --
duplicating its output. The name comes from the T-splitter used in plumbing
whose shape looks like the capital letter T.

One particular use-case is to snapshot data at an intermediate point in a
processing pipeline -- e.g. `thing1 | thing2 | tee output2.dat | thing3 |
thing4`.

Miller has a tee in two places: (1) a [verb](#verb) you can insert into a
Miller [then-chain](reference-main-then-chaining.md), and (2) an [output
statement](reference-dsl-output-statements.md) in the [Miller programming
language](miller-programming-language.md). Using the latter, you have the additional
option of using a tee-to file name which is variable, perhaps depending on the
current record. For example, if you have a large file with an `id` column, you
can split it into several files, one for each distinct `id`. See the [section
on tee statements](reference-dsl-output-statements.md#tee-statements) for an
example.

## terminator

Used in two senses:

(1) Refers to whichever character sequence terminates a [line](#line) of text,
such as newline/linefeed (LF) or a carriage-return-linefeed pair (CR/LF). See
also
[https://en.wikipedia.org/wiki/Newline](https://en.wikipedia.org/wiki/Newline).

(2) In some programming languages, such as C, C++, and Java, semicolons are
required after every statement; in others such as Python, they're not required
at all; in yet others, they're required _in between_ statements but are
optional after the last. Miller is in the third category, so we can say that
semicolons are [_separators_](#separator), not _terminators_, within the
[Miller programming language](miller-programming-language.md).

## toolkit

See [Unix toolkit](#unix-toolkit).

## true

A [keyword](#keyword) in the [Miller programming language](miller-programming-language.md) for the boolean
literal; signified by `True` in Python; in some languages (such as C) signified by
non-zero integer values.

## TSV

Stands for _tab-separated values_.
A popular [file format](file-formats.md#csvtsvasvusvetc) for tabular data
(tab-separated values) supported by Miller.

## UDF

A [user-defined function](reference-dsl-user-defined-functions.md) in the [Miller programming language](miller-programming-language.md).

## unflatten

To undo the [flatten](#flatten) operation, restoring map-valued and/or
array-valued fields encoded in CSV and other non-JSON [file
formats](file-formats.md) for JSON output.  See the [flatten/unflatten
page](flatten-unflatten.md).

## Unix toolkit

The term [_Unix toolkit_](https://en.wikipedia.org/wiki/List_of_Unix_commands)
refers to a collection of command-line programs present in Unix and Unix-like
operating systems, BSD variants, MacOS, etc. Examples include `awk`, `sed`,
`grep`, `cat`, and `cut`. Common characteristics include processing data files
one line at a time, reading input from one or more files, reading input from
standard input if no files are specified, writing output to standard output,
and connecting the output of one program to the input of another using
[pipes](https://en.wikipedia.org/wiki/Pipeline_(Unix)). Miller is designed
explicitly to work well in this paradigm alongside items in the Unix toolkit.
Moreover, several of Miller's [verbs](reference-verbs.md) are designed
to imitate some of the programs in the Unix toolkit, but with ability
to operate on richer [file formats](file-formats.md) such as [CSV](#csv), [TSV](#tsv),
[JSON](#json), and others.

## unnamed function

See [function literal](#function-literal).

## unset

A [keyword](#keyword) in the [Miller programming language](miller-programming-language.md)
for removing the definition of a local or out-of-stream variable, or for removing
a [key](#key) from the current [record](#record).

See the [DSL unset statements page](reference-dsl-unset-statements.md).

## unsparse

Transforming data so that all records have the same keys, by filling in default values.  See the
[record-heterogeneity
page](record-heterogeneity.md#sparse-data).

## value

The thing indexed by a [key](#key) in a [map](#map).  Miller values take one of
Miller's [data types](reference-main-data-types.md).  See also
[record](#record).

## var

A [keyword](#keyword) for
[type declaration](reference-dsl-variables.md#type-declarations-for-local-variables-function-parameter-and-function-return-values). It means a variable can have any type, which in itself is not useful; its usefulness comes from
letting you declare a new variable, in an inner scope, of the same name as another in an outer scope.

## variable

A way to access data by name within the [Miller programming language](miller-programming-language.md).
See the [DSL variables page](reference-dsl-variables.md).

## verb

One of the ways you ask Miller to transform your data as it
[processes](reference-main-overview.md) it.  Many of Miller's verbs such as
[`sort`](reference-verbs.md#sort) and [`cut`](reference-verbs.md#cut) are
[file-format-aware](file-formats.md) analogues of tools in the [Unix
toolkit](#unix-toolkit).

See the [List of verbs](reference-verbs.md) page.

## while

A [keyword](#keyword)  which is used to indicate the start of a
[while-loop](reference-dsl-control-structures.md), and also used in do-while
loops, in the [Miller programming language](miller-programming-language.md).

## XTAB

Stands for _transposed tabular_.  A Miller-specific [file
format](file-formats.md#xtab-vertical-tabular) for [key](#key)-[value](#value) pairs: it's a
vertical-tabular format useful for looking a files with a large number of
columns. Example: `mlr --icsv --oxtab head -n 1 widefile.csv`.

## zero-up

A way of indexing [arrays](#array). If `x=["a", "b", "c"]`, then using zero-up indexing,
`x[0]` is `"a"`, `x[1]` is `"b"`, and `x[2]` is `"c"`. Miller uses [one-up indexing](#one-up).

See also the [arrays page](reference-main-arrays.md), as well as the page on
[differences from other programming languages](reference-dsl-differences.md).

## ZLIB / .z

A [data-compression format supported by Miller](reference-main-compressed-data.md).
Files compressed using ZLIB compression normally end in `.z`.
