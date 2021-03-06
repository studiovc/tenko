# Tenko parser autogenerated test case

- From: tests/testcases/group_or_arrow/group/group2farrow_with_trailing_comma/in_non-assigned_group/autogen.md
- Path: tests/testcases/group_or_arrow/group/group2farrow_with_trailing_comma/in_non-assigned_group/gen/after_object_destruct_with_default/Infinity.md

> :: group or arrow : group : group2farrow with trailing comma : in non-assigned group : gen : after object destruct with default
>
> ::> Infinity

## Input

- `es = Infinity`

`````js
({a} = b,)
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in five parsing modes: sloppy, sloppy+annexb, strict script, module, module+annexb.

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Group contained a value that must destruct but this was not an arrow so it is invalid (at EOF)

start@1:0, error@1:0
╔══╦════════════════
 1 ║ ({a} = b,)
   ║ ^^^^^^^^^^------- error
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

_Output same as sloppy mode._

### Module goal with AnnexB

Parsed with the module goal with AnnexB rules enabled.

_Output same as sloppy mode._
