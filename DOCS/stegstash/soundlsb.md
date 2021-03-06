# soundlsb

> Auto-generated documentation for [stegstash.soundlsb](../../stegstash/soundlsb.py) module.

LSB for Sound

- [Stegstash](../README.md#stegstash-index) / [Modules](../README.md#stegstash-modules) / [stegstash](index.md#stegstash) / soundlsb
    - [decode](#decode)
    - [encode](#encode)
    - [extNotLossless](#extnotlossless)
    - [openSound](#opensound)
    - [simpleDecode](#simpledecode)
    - [simpleEncode](#simpleencode)
    - [writeSound](#writesound)

## decode

[[find in source code]](../../stegstash/soundlsb.py#L33)

```python
def decode(openPath, soundMapSeed, password='', zeroTerm=True, file=None):
```

decode data from a sound file using lsb steganography

#### Arguments

- `openPath` *string* - path to the stego-sound file to decode
- `soundMapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".
- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.

#### Returns

- `bytes` - data from the sound file

## encode

[[find in source code]](../../stegstash/soundlsb.py#L17)

```python
def encode(openPath, writePath, chars, soundMapSeed, password=''):
```

encode a sound file with data using lsb steganography

#### Arguments

- `openPath` *string* - path to the original sound file to open
- `writePath` *string* - path to write the stego-sound file
- `data` *string|bytes|<file>* - data to encode
- `soundMapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".

## extNotLossless

[[find in source code]](../../stegstash/soundlsb.py#L10)

```python
def extNotLossless(fileName):
```

Output the file extension not lossless error

## openSound

[[find in source code]](../../stegstash/soundlsb.py#L81)

```python
def openSound(path):
```

open a sound file

## simpleDecode

[[find in source code]](../../stegstash/soundlsb.py#L65)

```python
def simpleDecode(openPath, zeroTerm=True, file=None):
```

decode data from a sound file using lsb steganography

#### Arguments

- `openPath` *string* - path to the stego-sound file to decode
- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.

#### Returns

- `bytes` - data from the sound file

## simpleEncode

[[find in source code]](../../stegstash/soundlsb.py#L51)

```python
def simpleEncode(openPath, writePath, chars):
```

encode a sound file with data using lsb steganography

#### Arguments

- `openPath` *string* - path to the original sound file to open
- `writePath` *string* - path to write the stego-sound file
- `data` *string|bytes|<file>* - data to encode

## writeSound

[[find in source code]](../../stegstash/soundlsb.py#L100)

```python
def writeSound(path, sound, samplerate, shape):
```

Write a 1D numpy array to a sound file

#### Arguments

- `path` *string* - path to the sound file to save
- `sound` *numpy.array* - 1D numpy array containing sound data
- `samplerate` *int* - sample rate
- `shape` *Tuple(int)* - shape
