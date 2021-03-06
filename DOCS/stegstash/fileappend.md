# fileappend

> Auto-generated documentation for [stegstash.fileappend](../../stegstash/fileappend.py) module.

 append data to an image after the end
Files and byte(s) terminators

- [Stegstash](../README.md#stegstash-index) / [Modules](../README.md#stegstash-modules) / [stegstash](index.md#stegstash) / fileappend
    - [decode](#decode)
    - [detectSteg](#detectsteg)
    - [encode](#encode)
    - [extNotSupported](#extnotsupported)
    - [openFile](#openfile)
    - [writeFile](#writefile)

jpg: ÿÙ
png: IEND®B` (IEND.b`. - think only IEND is required)
gif:  ; (; according to wikipedia)

## decode

[[find in source code]](../../stegstash/fileappend.py#L38)

```python
def decode(openPath, password='', file=None):
```

decode data from a file by extracting data after end of file

#### Arguments

- `openPath` *string* - path to the stego-file to decode
- `password` *str, optional* - password to encrypt the data with. Defaults to "".
- `file` *<file>, optional* - file pointer. Defaults to None.

#### Returns

- `bytes` - data from the image

## detectSteg

[[find in source code]](../../stegstash/fileappend.py#L90)

```python
def detectSteg(openPath):
```

detect the use of file appended steganography

#### Arguments

- `openPath` *string* - path to the text file to analyse

#### Returns

- `boolean` - True if this lib has been used to hide data

## encode

[[find in source code]](../../stegstash/fileappend.py#L24)

```python
def encode(openPath, writePath, appendData, password=''):
```

encode a file with data by appending binary after the end of the file

#### Arguments

- `openPath` *string* - path to the original file to open
- `writePath` *string* - path to write the stego-file
- `appendData` *string|bytes|<file>* - data to encode
- `password` *str, optional* - password to encrypt the data with. Defaults to "".

## extNotSupported

[[find in source code]](../../stegstash/fileappend.py#L16)

```python
def extNotSupported(fileName):
```

Output the file extension not supported error

## openFile

[[find in source code]](../../stegstash/fileappend.py#L56)

```python
def openFile(path):
```

Open an file to bytes

#### Arguments

- `path` *string* - path to the file to open

#### Returns

- `bytes` - file data

## writeFile

[[find in source code]](../../stegstash/fileappend.py#L75)

```python
def writeFile(path, byteArr):
```

Write bytes to a file

#### Arguments

- `path` *string* - path to the file to save
- `byteArr` *bytes* - bytes to write to the file
