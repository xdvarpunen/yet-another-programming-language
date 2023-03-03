# yet-another-programming-language

[Try out here](https://xdvarpunen.github.io/yet-another-programming-language/)

## Syntax

```
<function-1-name> <parameter-1> ... <parameter-n>
.
.
.
<function-n-name> <parameter-1> ... <parameter-n>
```

- one function call per line
- divider can be space or punctuation mark or anything you need
- file extension can be anything you like

That's that.

## Features

- fast to learn
- fast to implement
- fast to port

## Example of use

```
define x 3
sum x 1
msgbox x
```

## Example of implementation

```javascript
let context = {};

function functionLibrary(functionName, parameters) {
    if (functionName == "msgbox") {
        if (Object.hasOwn(context, parameters[0])) {
            alert(context[parameters[0]]);
        } else {
            alert(parameters[0]);
        }
    } else if (functionName == "sum") {
        context[parameters[0]] = parseInt(context[parameters[0]]) + parseInt(parameters[1]);
    } else if (functionName == "define") {
        context[parameters[0]] = parameters[1];
    }
}

function interpret(sourceCode) {
    context = {};
    const rows = sourceCode.split("\n");
    rows.forEach(row => {
        const rowSplitted = row.split(" ");
        functionLibrary(rowSplitted[0], rowSplitted.slice(1, rowSplitted.length));
    });
}

function run() {
    const sourceCode = document.querySelector('textarea').value;
    interpret(sourceCode);
}
```
