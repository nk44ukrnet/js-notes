# js-notes
language notes

Internationalizing Dates (Intl) - [mdn link](Intl.DateTimeFormat)

Internalization of data (time, currency, numbers). User browser language ca be get from `navigator.language`

example: `const num = 123;`
`const options = = { style: 'currency', currency: 'EUR' }`
`console.log(navigator.language, new NumberFormat(navigator.language, options).format(num)`

`??` operator -> [mdn link](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing_operator)

`const foo = null ?? 'default string';`
`console.log(foo);`
`// expected output: "default string"`

`const baz = 0 ?? 42;`
`console.log(baz);`
`// expected output: 0`



### array methods

`[[1], [2]].flat($number)` - makes array flat. Example `[[1], [2]]`  =>  `[1,2]`
$number - by default set 1. If you need deeper - paste bigger number.

`.flatMap( function(item) {} )` - same as flat (flats only 1 level arrray. In the callback function - use .map() for arrays


### new Set([1,2,3,4])

Returns unique values from array `new Set([1,1,1,4])` => `[1,4]` - this will be not array anymore. So you can make it array again by  `let arrAgain = [...setVariable];`

### call
`const personObj = {name: 'Sarah'}`

`function logName(greet = 'yo'){ console.log (greet, this.name); }`

Usage: `logName.call(personObj, 'hi')`

calls function with  ___this___ related to object

### bind
Creates another function, based on previous (binds this, can also bind other parameters)

Usage (based on call example) 
`const personObj = {name: 'Sarah'}`

`function logName(greet = 'yo'){ console.log (greet, this.name); }`

`const logNamePredifined =  logName.bind(personObj, 'Buenos dias ')`

`logNamePredifined();`

### String.prototype.padStart() and String.prototype.padEnd()

adds padding to string (__not css padding__), example:
`'abc'.padStart(10);         // "       abc"`

`'abc'.padStart(10, "foo");  // "foofoofabc"`

`'abc'.padStart(6,"123465"); // "123abc"`

`'abc'.padStart(8, "0");     // "00000abc"`

'`abc'.padStart(1);          // "abc"`

Usefula case: When you need to display time like : `01:59` format

`'1'.padStart(2, '0');` => will be result __'01'__ as string

### setting css :root { --primary: #eee }
`document.documentElement.style.setProperty('--primary', '#000')`

Can be usefull to create dark theme (by changing css variables colors);
