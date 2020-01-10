# Tenko parser test case

- Path: tests/testcases/strict_mode/directive_headers/octal_escape/parenless_arrow_param_name/package_as_func_param_no_escape_with_directive.md

> :: strict mode : directive headers : octal escape : parenless arrow param name
>
> ::> package as func param no escape with directive
>
> Octal escapes are okay in sloppy mode. 
>
> `package` is a keyword only in strict mode

## Input


`````js
package => { "use strict"; }
`````

## Output

_Note: the whole output block is auto-generated. Manual changes will be overwritten!_

Below follow outputs in four parsing modes: sloppy mode, strict mode script goal, module goal, web compat mode (always sloppy).

Note that the output parts are auto-generated by the test runner to reflect actual result.

### Sloppy mode

Parsed with script goal and as if the code did not start with strict mode header.

`````
throws: Parser error!
  Can only declare use strict if func params are "simple"

start@1:0, error@1:27
╔══╦═════════════════
 1 ║ package => { "use strict"; }
   ║                            ^------- error
╚══╩═════════════════

`````

### Strict mode

Parsed with script goal but as if it was starting with `"use strict"` at the top.

`````
throws: Parser error!
  Cannot use this name (`package`) as a variable name because: Cannot use this reserved word as a variable name in strict mode

start@1:0, error@1:0
╔══╦════════════════
 1 ║ package => { "use strict"; }
   ║ ^^^^^^^------- error
╚══╩════════════════

`````


### Module goal

Parsed with the module goal.

_Output same as strict mode._

### Web compat mode

Parsed in sloppy script mode but with the web compat flag enabled.

_Output same as sloppy mode._