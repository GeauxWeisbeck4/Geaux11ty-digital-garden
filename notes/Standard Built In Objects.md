- # Array Buffer
    - The **ArrayBuffer** object is used to represent a generic, fixed-length raw binary data buffer.
    - It is an array of bytes, often referred to in other languages as a "byte array". You cannot directly manipulate the contents of an ArrayBuffer; instead, you create one of the [typed array objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray) or a [DataView](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/DataView) object which represents the buffer in a specific format, and use that to read and write the contents of the buffer.
    - The [ArrayBuffer()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer/ArrayBuffer) constructor creates a new ArrayBuffer of the given length in bytes. You can also get an array buffer from existing data, for example, from a [Base64](https://developer.mozilla.org/en-US/docs/Glossary/Base64) string or [from a local file](https://developer.mozilla.org/en-US/docs/Web/API/FileReader/readAsArrayBuffer).
- # Unit8Array
    - The **Uint8Array** typed array represents an array of 8-bit unsigned integers. The contents are initialized to 0. Once established, you can reference elements in the array using the object's methods, or using standard array index syntax (that is, using bracket notation).
        - ```javascript
// From a length
const uint8 = new Uint8Array(2);
uint8[0] = 42;
console.log(uint8[0]); // 42
console.log(uint8.length); // 2
console.log(uint8.BYTES_PER_ELEMENT); // 1

// From an array
const x = new Uint8Array([21, 31]);
console.log(x[1]); // 31

// From another TypedArray
const y = new Uint8Array(x);
console.log(y[0]); // 21

// From an ArrayBuffer
const buffer = new ArrayBuffer(8);
const z = new Uint8Array(buffer, 1, 4);
console.log(z.byteOffset); // 1

// From an iterable
const iterable = (function* () {
  yield* [1, 2, 3];
})();
const uint8FromIterable = new Uint8Array(iterable);
console.log(uint8FromIterable);
// Uint8Array [1, 2, 3]
```
    - 
