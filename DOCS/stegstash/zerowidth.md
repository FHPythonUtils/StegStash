# zerowidth

> Auto-generated documentation for [stegstash.zerowidth](../../stegstash/zerowidth.py) module.

Uses zero width chars to hide data

- [Stegstash](../README.md#stegstash-index) / [Modules](../README.md#stegstash-modules) / [stegstash](index.md#stegstash) / zerowidth
    - [decode](#decode)
    - [decodeCharZero](#decodecharzero)
    - [detectSteg](#detectsteg)
    - [encode](#encode)
    - [encodeCharZero](#encodecharzero)
    - [getUtf8Size](#getutf8size)
    - [readUtf8](#readutf8)
    - [simpleDecode](#simpledecode)
    - [simpleEncode](#simpleencode)
    - [visual](#visual)
    - [writeUtf8](#writeutf8)

One similar project uses the following code points:
Unicode u200b to u200f
zero width space
zero width non joiner
zero width joiner
left to right mark
right to left mark

These are invisible in VSCode, Notepad.exe and PythonIDLE

See the table below for a comparison of various glyphs in a series of popular text
editors

|Char Code|   Char Name|Notepad.exe|VSCode|PythonIDLE|KWrite|EMACS|<safe>|MsWord|    Utf8|
|---------|------------|-----------|------|----------|------|-----|------|------|--------|
|<control>|   <control>|          x|     x|         x|     x|    x|     x|     x|        |
|u00ad    |  SoffHyphen|          x|     +|         x|     x|    x|     x|     x|        |
|u034f    |   CombiningGraphemeJoiner|+| +|         +|     +|    x|     x|     +|        |
|u200b    |     ZWSpace|          +|     +|         +|     +|    +|     +|     +|E2 80 8B|
|u200c    | ZWNonJoiner|          +|     +|         +|     +|    +|     +|     +|E2 80 8C|
|u200d    |    ZWJoiner|          +|     +|         +|     +|    +|     +|     +|E2 80 8D|
|u200e    |     LTRMark|          +|     +|         +|     +|    +|     +|     +|E2 80 8E|
|u200f    |     RTLMark|          +|     +|         +|     +|    +|     +|     +|E2 80 8F|
|u202a    |LTREmbedding|          +|     +|         +|     +|    +|     +|     +|E2 80 AA|
|u202b    |RTLEmbedding|          +|     +|         +|     +|    +|     +|     +|        |
|u202c    |  PopDirectionalFormatting|+| +|         +|     +|    +|     +|     +|E2 80 AC|
|u202d    | LTROverride|          +|     +|         +|     +|    +|     +|     +|E2 80 AD|
|u202e    | RTLOverride|          x|     x|         +|     x|    x|     x|     x|        |
|u2060    |  WordJoiner|          x|     +|         +|     +|    +|     x|     +|        |
|u2061    |   FunctionApplication|+|     +|         +|     +|    +|     +|     x|E2 81 A1|
|u2062    |        InvisibleTimes|+|     +|         +|     +|    +|     +|     x|E2 81 A2|
|u2063    |    InvisibleSeperator|+|     +|         +|     +|    +|     +|     x|E2 81 A3|
|u2064    |InvisiblePlue|         +|     +|         +|     +|    +|     +|     x|E2 81 A4|
|u2065    |   <unknown>|          x|     +|         x|     +|    x|     x|     x|        |
|u2066    |  LTRIsolate|          x|     +|         x|     +|    +|     x|     x|        |
|u2067    |  RTLIsolate|          x|     +|         x|     +|    +|     x|     x|        |
|u2068    |    FirstStrongIsolate|x|     +|         x|     +|    +|     x|     x|        |
|u2069    | PopDirectionalIsolate|x|     +|         x|     +|    +|     x|     x|        |
|u206a    |  InhibitSymmetricSwapping|+| +|         +|     +|    +|     +|     x|E2 81 AA|
|u206b    | ActivateSymmetricSwapping|+| +|         +|     +|    +|     +|     x|E2 81 AB|
|u206c    | InhibitArabicFormSwapping|+| +|         +|     +|    +|     +|     x|E2 81 AC|
|u206d    |ActivateArabicFormSwapping|+| +|         +|     +|    +|     +|     x|E2 81 AD|
|u206e    |   NationalDigitShapes|+|     +|         +|     +|    +|     +|     x|E2 81 AE|
|u206f    |    NominalDigitShapes|+|     +|         +|     +|    +|     +|     x|E2 81 AF|
|u2068    |    FirstStrongIsolate|x|     +|         x|     +|    +|     x|     x|        |

The likes of vim/gvim show these up but a typical user is unlikely to be using
those text editors.

Though not a text editor, Microsoft Word seems pretty good at higlighting some
of these chars (at least better than initially expected). There is a possibility
that a user may have configured word to open a text file (though not completely
likely). To mitigate this slim risk a safe mode will be added to disable use of
these chars

## decode

[[find in source code]](../../stegstash/zerowidth.py#L99)

```python
def decode(
    openPath,
    mapSeed,
    password='',
    zeroTerm=True,
    file=None,
    safe=True,
):
```

decode data from a text file using zero width chars

#### Arguments

- `openPath` *string* - path to the stego-text file to decode
- `mapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".
- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.
- `safe` *boolean, optional* - use a reduced set of chars to show in fewer
editors. Defaults to True.

#### Returns

- `bytes` - data from the text file

## decodeCharZero

[[find in source code]](../../stegstash/zerowidth.py#L189)

```python
def decodeCharZero(fileData, pointer, safe=True):
```

 decode a series of zero width chars as a char such that   is read
from f o o bar

## detectSteg

[[find in source code]](../../stegstash/zerowidth.py#L241)

```python
def detectSteg(openPath):
```

detect the use of zero width char steganography

#### Arguments

- `openPath` *string* - path to the text file to analyse

#### Returns

- `boolean` - True if this lib has been used to hide data

## encode

[[find in source code]](../../stegstash/zerowidth.py#L71)

```python
def encode(openPath, writePath, data, mapSeed, password='', safe=True):
```

encode a text file with data using zero width chars

#### Arguments

- `openPath` *string* - path to the original text file to open
- `writePath` *string* - path to write the stego-text file
- `data` *string|bytes|<file>* - data to encode
- `mapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".
- `safe` *boolean, optional* - use a reduced set of chars to show in fewer
editors. Defaults to True.

## encodeCharZero

[[find in source code]](../../stegstash/zerowidth.py#L176)

```python
def encodeCharZero(fileData, pointer, char, safe=True):
```

 encode a char as a series of zero width chars such that the result looks
like foobar -> f o o bar

## getUtf8Size

[[find in source code]](../../stegstash/zerowidth.py#L224)

```python
def getUtf8Size(byteStream, pointer):
```

get the size of the next utf8 char

## readUtf8

[[find in source code]](../../stegstash/zerowidth.py#L211)

```python
def readUtf8(pointer, byteStream):
```

 read the next zero char and advance the pointer
1 utf8: 0
2 utf8: 110
3 utf8: 1110
4 utf8: 11110

## simpleDecode

[[find in source code]](../../stegstash/zerowidth.py#L150)

```python
def simpleDecode(openPath, zeroTerm=True, file=None, safe=True):
```

decode data from a text file using zero width chars

#### Arguments

- `openPath` *string* - path to the stego-text file to decode
- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.
- `safe` *boolean, optional* - use a reduced set of chars to show in fewer
editors. Defaults to True.

#### Returns

- `bytes` - data from the text file

## simpleEncode

[[find in source code]](../../stegstash/zerowidth.py#L131)

```python
def simpleEncode(openPath, writePath, data, safe=True):
```

encode a text file with data using zero width chars

#### Arguments

- `openPath` *string* - path to the original text file to open
- `writePath` *string* - path to write the stego-text file
- `data` *string|bytes|<file>* - data to encode
- `safe` *boolean, optional* - use a reduced set of chars to show in fewer
editors. Defaults to True.

## visual

[[find in source code]](../../stegstash/zerowidth.py#L256)

```python
def visual(openPath, imgPath):
```

Visualize the use of homoglyph stegonography.

#### Arguments

- `openPath` *string* - path to the text file to analyse
- `imgPath` *string* - image file path

## writeUtf8

[[find in source code]](../../stegstash/zerowidth.py#L202)

```python
def writeUtf8(pointer, newBytes, byteStream):
```

 write a series of utf8 bytes after an existing char and advance the
pointer
