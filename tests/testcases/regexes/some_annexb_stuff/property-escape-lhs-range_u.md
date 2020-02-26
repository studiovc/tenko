# Tenko parser test case

- Path: tests/testcases/regexes/some_annexb_stuff/property-escape-lhs-range_u.md

> :: regexes : some annexb stuff
>
> ::> property-escape-lhs-range u
>
> From test262/test/built-ins/RegExp/property-escapes/character-class-range-no-dash-start.js
>
> Only applies to regex with u-flag

## FAIL

## Input

`````js
/[\p{Hex_Digit}-\uFFFF]/u;
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Lexer error!
    Regex: The `\p` property escape is only legal with a u-flag, or as a webcompat edge case; Character class escapes `\d \D \s \S \w \W \p \P` not allowed in ranges with u

start@1:0, error@1:0
╔══╦════════════════
 1 ║ /[\p{Hex_Digit}-\uFFFF]/u;
   ║ ^^^^^^^^^^^^^^^^^^^^^^^^------- error
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
throws: Lexer error!
    Regex: Character class escapes `\d \D \s \S \w \W \p \P` not allowed in ranges with u; Regex contained syntax that is invalid with the u-flag but the u-flag was present

start@1:0, error@1:0
╔══╦════════════════
 1 ║ /[\p{Hex_Digit}-\uFFFF]/u;
   ║ ^^^^^^^^^^^^^^^^^^^^^^^^^------- error
╚══╩════════════════

`````

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as sloppy mode with annexB._