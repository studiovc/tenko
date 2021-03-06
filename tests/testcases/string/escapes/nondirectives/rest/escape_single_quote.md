# Tenko parser test case

- Path: tests/testcases/string/escapes/nondirectives/rest/escape_single_quote.md

> :: string : escapes : nondirectives : rest
>
> ::> escape single quote
>
> Checks the .value and .rawValue, making sure they are not directives

## Input

`````js
debugger;
'some \' quote';
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
  loc:{start:{line:1,column:0},end:{line:2,column:16},source:''},
  body: [
    {
      type: 'DebuggerStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:9},source:''}
    },
    {
      type: 'ExpressionStatement',
      loc:{start:{line:2,column:0},end:{line:2,column:16},source:''},
      expression: {
        type: 'Literal',
        loc:{start:{line:2,column:0},end:{line:2,column:15},source:''},
        value: "some ' quote",
        raw: "'some \\' quote'"
      }
    }
  ]
}

tokens (5x):
       ID_debugger PUNC_SEMI STRING_SINGLE PUNC_SEMI
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
debugger;
('some \' quote');
````

Produces same AST
