# Encode Decode

A Javascript object to encode and/or decode html characters using HTML or
Numeric entities that handles double or partial encoding.

This is an npm published version of [Robert Reid's
original](http://www.strictly-software.com/htmlencode) - full credit to Robert.

## Example

_Modified from the [original
documentation](http://www.strictly-software.com/htmlencode)_

```javascript
var Encoder = require('encode-decode');

// set the type of encoding to numerical entities e.g & instead of &
Encoder.EncodeType = "numerical";

// or to set it to encode to html entities e.g & instead of &
Encoder.EncodeType = "entity";

// HTML encode text from an input element
// This will prevent double encoding.
var encoded = Encoder.htmlEncode(document.getElementById('input'));

// To encode but to allow double encoding which means any existing entities such as
// &amp; will be converted to &amp;amp;
var dblEncoded = Encoder.htmlEncode(document.getElementById('input'),true);

// Decode the now encoded text
var decoded = Encoder.htmlDecode(encoded);

// Check whether the text still contains HTML/Numerical entities
var containsEncoded = Encoder.hasEncoded(decoded);
```

## Usage

_Taken from the [original
documentation](http://www.strictly-software.com/htmlencode)_

> There are a number of useful functions within the object which I will outline
> here:
> * **`HTML2Numerical`**: Converts HTML entities to their numerical equivalents.
> * **`NumericalToHTML`**: Converts numerical entities to their HTML
>   equivalents.
> * **`numEncode`**: Numerically encodes unicode characters.
> * **`htmlDecode`**: Decodes HTML encoded text to its original state.
> * **`htmlEncode`**: Encodes HTML to either numerical or HTML entities. This is
>   determined by the EncodeType property.
> * **`XSSEncode`**: Encodes the basic characters used in XSS attacks to malform
>   HTML.
> * **`correctEncoding`**: Corrects any double encoded ampersands.
> * **`stripUnicode`**: Removes all unicode characters.
> * **`hasEncoded`**: Returns true if a string contains html encoded entities
>   within it.

## Motivation

_Taken from the [original
documentation](http://www.strictly-software.com/htmlencode)_

> One of the things that I have found strange about Javascript is its lack of
> inbuilt functions to handle **HTML encoding and decoding**. Most server side
> languages have this functionality built into them but Javascript has escape,
> encodeURIComponent, encodeURI, unescape, decodeURIComponent and decodeURI
> functions which are aimed at making strings portable and for encoding URIs and
> URI parameters but there is no function for **HTML encoding**.
> 
> Now you may think well there's not much demand for a **Javascript HTMLEncode
> and HTMLDecode function** as any textual content that needs encoding should be
> done server-side before the HTML page is rendered and I would have agreed with
> you not long ago. However I have started working more and more with AJAX and
> especially RSS feeds and other client side delivered content such as Googles
> AJAX APIs and I have found more and more the need to **reformat content**
> delivered from external sources especially by **HTML encoding or decoding
> content client side using Javascript**.
> 
> For more details about reformating content with Javascript and the problems
> associated with simple replace statements you can read [my related blog
> article](http://blog.strictly-software.com/2009/07/html-encoding-and-decoding-using.html).

## License

Dual GPL v2 or MIT licence.
