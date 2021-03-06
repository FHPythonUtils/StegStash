# imagelsb

> Auto-generated documentation for [stegstash.imagelsb](../../stegstash/imagelsb.py) module.

encode and decode methods

- [Stegstash](../README.md#stegstash-index) / [Modules](../README.md#stegstash-modules) / [stegstash](index.md#stegstash) / imagelsb
    - [decode](#decode)
    - [encode](#encode)
    - [extNotLossless](#extnotlossless)
    - [openImg](#openimg)
    - [simpleDecode](#simpledecode)
    - [simpleEncode](#simpleencode)
    - [visual](#visual)
    - [writeImg](#writeimg)

## decode

[[find in source code]](../../stegstash/imagelsb.py#L33)

```python
def decode(openPath, imageMapSeed, password='', zeroTerm=True, file=None):
```

decode data from an image using lsb steganography

#### Arguments

- `openPath` *string* - path to the stego-image to decode
- `imageMapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".
- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.

#### Returns

- `bytes` - data from the image

## encode

[[find in source code]](../../stegstash/imagelsb.py#L17)

```python
def encode(openPath, writePath, data, imageMapSeed, password=''):
```

encode an image with data using lsb steganography

#### Arguments

- `openPath` *string* - path to the original image to open
- `writePath` *string* - path to write the stego-image
- `data` *string|bytes|<file>* - data to encode
- `imageMapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".

## extNotLossless

[[find in source code]](../../stegstash/imagelsb.py#L10)

```python
def extNotLossless(fileName):
```

Output the file extension not lossless error

## openImg

[[find in source code]](../../stegstash/imagelsb.py#L81)

```python
def openImg(path):
```

Open an image as a numpy array

#### Arguments

- `path` *string* - path to the image to open

#### Returns

numpy.array, (int, int), string: A 1D numpy array containing image
pixels, image size, image mode

## simpleDecode

[[find in source code]](../../stegstash/imagelsb.py#L65)

```python
def simpleDecode(openPath, zeroTerm=True, file=None):
```

decode data from an image using lsb steganography

#### Arguments

- `openPath` *string* - path to the stego-image to decode
- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.

#### Returns

- `bytes` - data from the image

## simpleEncode

[[find in source code]](../../stegstash/imagelsb.py#L51)

```python
def simpleEncode(openPath, writePath, data):
```

encode an image with data using lsb steganography

#### Arguments

- `openPath` *string* - path to the original image to open
- `writePath` *string* - path to write the stego-image
- `data` *string|bytes|<file>* - data to encode

## visual

[[find in source code]](../../stegstash/imagelsb.py#L118)

```python
def visual(openPath, imgPath):
```

Visualize the use of lsb stegonography.

#### Arguments

- `openPath` *string* - path to the text file to analyse
- `imgPath` *string* - image file path

## writeImg

[[find in source code]](../../stegstash/imagelsb.py#L102)

```python
def writeImg(path, image, imageSize, mode):
```

Write a 1D numpy array to a file

#### Arguments

- `path` *string* - path to the image to save
- `image` *numpy.array* - 1D numpy array containing image pixels
imageSize ((int, int)): size of the image
- `mode` *string* - PIL Image mode typically one of "RGBA", "RGB", "PA", "P"
