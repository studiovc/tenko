# Tenko parser test case

- Path: tests/testcases/lexer_cases/error_reporting/long_line/long_line.md

> :: lexer cases : error reporting : long line
>
> ::> long line
>
> Make sure the code frame for an error on a long line (often seen in minified code) is properly cut
>
> The input is deliberately padded for this reason (the code frame will cover 100 bytes left and right of the error range)

## Input

`````js
_0_0123456789_1_0123456789_2_0123456789_3_0123456789_4_0123456789_5_0123456789_6_0123456789_7_0123456789_8_0123456789_9_0123456789_10_0123456789_11_0123456789_12_0123456789_13_0123456789_14_0123456789_15_0123456789_16_0123456789_17_0123456789_18_0123456789_19_0123456789_20
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
ast: {
  type: 'Program',
  loc:{start:{line:1,column:0},end:{line:1,column:273},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:273},source:''},
      expression: {
        type: 'Identifier',
        loc:{start:{line:1,column:0},end:{line:1,column:273},source:''},
        name: '_0_0123456789_1_0123456789_2_0123456789_3_0123456789_4_0123456789_5_0123456789_6_0123456789_7_0123456789_8_0123456789_9_0123456789_10_0123456789_11_0123456789_12_0123456789_13_0123456789_14_0123456789_15_0123456789_16_0123456789_17_0123456789_18_0123456789_19_0123456789_20'
      }
    }
  ]
}

tokens (3x):
       IDENT ASI
`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

_Output same as sloppy mode._

### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._

## AST Printer

Printer output different from input [sloppy]:

````js
_0_0123456789_1_0123456789_2_0123456789_3_0123456789_4_0123456789_5_0123456789_6_0123456789_7_0123456789_8_0123456789_9_0123456789_10_0123456789_11_0123456789_12_0123456789_13_0123456789_14_0123456789_15_0123456789_16_0123456789_17_0123456789_18_0123456789_19_0123456789_20;
````

Produces same AST