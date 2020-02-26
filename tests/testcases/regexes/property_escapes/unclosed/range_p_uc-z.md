# Tenko parser test case

- Path: tests/testcases/regexes/property_escapes/unclosed/range_p_uc-z.md

> :: regexes : property escapes : unclosed
>
> ::> range p uc-z
>
> 

## Input

`````js
/[\P-Z]/
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Lexer error!
    Regex: Property escape `\p` must start with a curly bracket

start@1:0, error@1:0
╔══╦════════════════
 1 ║ /[\P-Z]/
   ║ ^^^^^^^^------- error
╚══╩════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

_Output same as sloppy mode._

### Module goal

Parsed with the module goal.

_Output same as sloppy mode._

### Sloppy mode with AnnexB

Parsed with script goal with AnnexB rules enabled and as if the code did not start with strict mode header.

`````
ast: {
  type: 'Program',
  loc:{start:{line:1,column:0},end:{line:1,column:8},source:''},
  body: [
    {
      type: 'ExpressionStatement',
      loc:{start:{line:1,column:0},end:{line:1,column:8},source:''},
      expression: {
        type: 'Literal',
        loc:{start:{line:1,column:0},end:{line:1,column:8},source:''},
        value: null,
        regex: { pattern: '[\\P-Z]', flags: '' },
        raw: '/[\\P-Z]/'
      }
    }
  ]
}

tokens (3x):
       REGEXN ASI
`````

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as sloppy mode with annexB._

## AST Printer

Printer output different from input [sloppy][annexb:yes]:

````js
/[\P-Z]/;
````

Produces same AST