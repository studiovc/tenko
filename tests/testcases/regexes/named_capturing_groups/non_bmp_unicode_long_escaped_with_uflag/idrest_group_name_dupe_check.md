# Tenko parser test case

- Path: tests/testcases/regexes/named_capturing_groups/non_bmp_unicode_long_escaped_with_uflag/idrest_group_name_dupe_check.md

> :: regexes : named capturing groups : non bmp unicode long escaped with uflag
>
> ::> idrest group name dupe check
>
> This checks whether `\u{1D7D0}` / `\uD835\uDFD0` is accepted inside a valid group
>
> It should fail because the name, canonically, is the same

## PASS

## Input

`````js
/(?<abc\u{1D7D0}def>foo\k<abc\uD835\uDFD0def>)/u
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
ast: {
  type: 'Program',
  loc:{start:{line:1,column:0},end:{line:1,column:48},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:48},source:''},
      expression: {
        type: 'Literal',
        loc:{start:{line:1,column:0},end:{line:1,column:48},source:''},
        value: null,
        regex: {
          pattern: '(?<abc\\u{1D7D0}def>foo\\k<abc\\uD835\\uDFD0def>)',
          flags: 'u'
        },
        raw: '/(?<abc\\u{1D7D0}def>foo\\k<abc\\uD835\\uDFD0def>)/u'
      }
    }
  ]
}

tokens (3x):
       REGEXU ASI
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

_Output same as sloppy mode._

### Sloppy mode with AnnexB

Parsed with script goal with AnnexB rules enabled and as if the code did not start with strict mode header.

_Output same as sloppy mode._

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as sloppy mode._

## AST Printer

Printer output different from input [sloppy][annexb:no]:

````js
/(?<abc\u{1D7D0}def>foo\k<abc\uD835\uDFD0def>)/u;
````

Produces same AST
