
#### Define Your Argumements: 
```
let args = [
    { arg: '-d', name: 'debug', type: 'boolean', default: true }, 
    { arg: '-p', name: 'port', type: 'number', default: 8080 },
    { arg: '-h', name: 'host', type: 'string', default: '0.0.0.0' },
];
```
#### Call Arg Parser:
```
// $your-command /home /usr -d -p 4000  

const argParser = require('mr-arg-parser');

let parsed = argParser(args);

console.log(parsed)
/*
{ 
  _: [ '/home', '/usr' ],
  host: '0.0.0.0',
  port: '4000',
  debug: true 
}
*/

```
#### Arguement Definition Properties:
* __arg__: how the argument should be specified on the command line. 
* __name__: how the arguement value shoud be displayed in the parsers output.
* __type__: one of the following: ['array', 'boolean', 'string', 'number']
* __default__: (optional) specifies default value for the arguement.

Array type arguements will contain all values from the arguements specifier until the parser comes across another argument specifier. 

Values Before the first argument specifier are included in the parsers output as the "_" property.  


