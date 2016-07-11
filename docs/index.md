<a name="module_lib/util"></a>

## lib/util
Workflow utility module used to format the return and error objects, and
contains some other utility functions such as a sync loop and compare.

**Version**: 0.1.0  
**Author:** Brent Gordon  

* [lib/util](#module_lib/util)
    * [~success(message, [data])](#module_lib/util..success) ⇒ <code>Object</code>
    * [~warn(message, [data])](#module_lib/util..warn) ⇒ <code>Object</code>
    * [~error(code, message)](#module_lib/util..error) ⇒ <code>Object</code>
    * [~syncLoop(iterations, process, exit)](#module_lib/util..syncLoop) ⇒ <code>Object</code>

<a name="module_lib/util..success"></a>

### lib/util~success(message, [data]) ⇒ <code>Object</code>
Success block return object, contains a message and optional data object.

**Kind**: inner method of <code>[lib/util](#module_lib/util)</code>  
**Returns**: <code>Object</code> - - with message and data properties  

| Param | Type | Description |
| --- | --- | --- |
| message | <code>string</code> | the success message |
| [data] | <code>string</code> &#124; <code>Object</code> | the success returned data |

**Example**  
```js
// Return success without a data block
var success = util.success('Success message goes here...');
```
<a name="module_lib/util..warn"></a>

### lib/util~warn(message, [data]) ⇒ <code>Object</code>
Warning block return object, contains a message and optional data object.

**Kind**: inner method of <code>[lib/util](#module_lib/util)</code>  
**Returns**: <code>Object</code> - with message and data properties, and logs the warning to the console.  

| Param | Type | Description |
| --- | --- | --- |
| message | <code>string</code> | the warning message |
| [data] | <code>string</code> &#124; <code>Object</code> | the returned data |

**Example**  
```js
// Return success without a data block
var success = util.warn('Warning message goes here...');
```
<a name="module_lib/util..error"></a>

### lib/util~error(code, message) ⇒ <code>Object</code>
Error block JS error object, contains a code and message for the error.

**Kind**: inner method of <code>[lib/util](#module_lib/util)</code>  
**Returns**: <code>Object</code> - with a code and message properties.  

| Param | Type | Description |
| --- | --- | --- |
| code | <code>string</code> | the error code |
| message | <code>string</code> | the error message |

**Example**  
```js
var success = util.error('Error001','Error message goes here...');
```
<a name="module_lib/util..syncLoop"></a>

### lib/util~syncLoop(iterations, process, exit) ⇒ <code>Object</code>
A loop which can loop X amount of times, which carries out
asynchronous code, but waits for that code to complete before looping.

**Kind**: inner method of <code>[lib/util](#module_lib/util)</code>  
**Returns**: <code>Object</code> - the loop control object.  

| Param | Type | Description |
| --- | --- | --- |
| iterations | <code>number</code> | the number of iterations to carry out |
| process | <code>function</code> | the code/function we're running for every iteration |
| exit | <code>function</code> | an optional callback to carry out once the loop has completed |

**Example**  
```js
util.syncLoop(5, function(loop){
	var counter = loop.iteration();
	// Add async calls here..

}, function(){
	// On complete perform actions here...

});
```
