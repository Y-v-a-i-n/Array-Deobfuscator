# A simple Array Deobfuscator in JavaScript that I made just for fun and out of boredom 
this obfuscation retrieves all values (strings) from the original program to store them in an array and replace the strings of the original program by the call of the string in the example array: 
original program : 
```js
console.log("hello")
```
obfuscated program : 
```js
var cuckoo = ["hello"];
console.log(cuckoo[0])
```
this obfuscation is also based on the fact that in JavaScript you can also write like this : 
```js
console["log"]("hello")
```
, that adds one more string to add in the array, and finally this obfuscation uses a low level value protection (hexadecimal encoding of the values in the array : "\x48\x65\x6C\x6F") to get to the point : 
original program : 
```js
console.log("hello");
```
obfuscated program :
```js
var _0xf476=["\x48\x65\x6C\x6C\x6F","\x6C\x6F\x67"];
console[_0xf476[1]](_0xf476[0]);
```
to unobfuscate this you just have to get the array _0xf476 and then display all the values and replace them, for example 
```js
_0xf476[1]="\x6C\x6F\x67"="log"
```
and 
```js
_0xf476[0]="\x48\x65\x6C\x6C\x6F"="hello"
```
once replaced (remember to remove the array which is useless after that) it should look like this : 
```js
console["log"]("Hello");
```
you can make the code look a bit nicer by replacing 
```js
onsole["log"]
```
with
```js
console.log
```
### How to launch Array Deobfuscator : 

* you must first install electronJs on your machine
```sh
$ npm install electron -g
```
* then you have to run the program with electron, for that you can run this command at the location of the index.js file, you can also run run.bat or run.sh
```sh
$ electron index.js
```
![image](https://cdn.discordapp.com/attachments/1025769112221270050/1053092297706836069/image.png)