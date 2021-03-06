# homoglyphs

> Auto-generated documentation for [stegstash.homoglyphs](../../stegstash/homoglyphs.py) module.

encode a text file using homoglyphs

- [Stegstash](../README.md#stegstash-index) / [Modules](../README.md#stegstash-modules) / [stegstash](index.md#stegstash) / homoglyphs
    - [decode](#decode)
    - [decodeGlyph](#decodeglyph)
    - [detectSteg](#detectsteg)
    - [encode](#encode)
    - [encodeGlyph](#encodeglyph)
    - [simpleDecode](#simpledecode)
    - [simpleEncode](#simpleencode)
    - [visual](#visual)

## decode

[[find in source code]](../../stegstash/homoglyphs.py#L95)

```python
def decode(openPath, mapSeed, password='', zeroTerm=True, file=None):
```

decode data from an text file using homoglyphs

#### Arguments

- `openPath` *string* - path to the stego-text file to decode
- `mapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".
- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.

#### Returns

- `bytes` - data from the text file

## decodeGlyph

[[find in source code]](../../stegstash/homoglyphs.py#L135)

```python
def decodeGlyph(fileData, position, byte, shift):
```

decode a single glyph (1/8th of hidden data)

## detectSteg

[[find in source code]](../../stegstash/homoglyphs.py#L144)

```python
def detectSteg(openPath):
```

Detect the use of homoglyph stegonography.

False positives can be easily triggered (this checks for non ascii chars)

#### Arguments

- `openPath` *string* - path to the text file to analyse

#### Returns

- `boolean` - True if this lib has been used to hide data

## encode

[[find in source code]](../../stegstash/homoglyphs.py#L63)

```python
def encode(openPath, writePath, data, mapSeed, password=''):
```

encode a text file with data using homoglyphs

#### Arguments

- `openPath` *string* - path to the original text file to open
- `writePath` *string* - path to write the stego-text file
- `data` *string* - data to encode
- `mapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".

## encodeGlyph

[[find in source code]](../../stegstash/homoglyphs.py#L127)

```python
def encodeGlyph(fileData, position, byte, shift):
```

encode a single glyph (1/8th of hidden data)

## simpleDecode

[[find in source code]](../../stegstash/homoglyphs.py#L34)

```python
def simpleDecode(openPath, zeroTerm=True, file=None):
```

decode data from an text file using homoglyphs

#### Arguments

- `openPath` *string* - path to the stego-text file to decode
- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.

#### Returns

- `bytes` - data from the text file

## simpleEncode

[[find in source code]](../../stegstash/homoglyphs.py#L10)

```python
def simpleEncode(openPath, writePath, data):
```

encode a text file with data using homoglyphs

#### Arguments

- `openPath` *string* - path to the original text file to open
- `writePath` *string* - path to write the stego-text file
- `data` *string|bytes|<file>* - data to encode

## visual

[[find in source code]](../../stegstash/homoglyphs.py#L161)

```python
def visual(openPath, imgPath):
```

Visualize the use of homoglyph stegonography.

#### Arguments

- `openPath` *string* - path to the text file to analyse
- `imgPath` *string* - image file path
