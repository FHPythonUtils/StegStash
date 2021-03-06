# lsb

> Auto-generated documentation for [stegstash.lsb](../../stegstash/lsb.py) module.

common lsb functions

- [Stegstash](../README.md#stegstash-index) / [Modules](../README.md#stegstash-modules) / [stegstash](index.md#stegstash) / lsb
    - [LSB](#lsb)
        - [LSB().decode](#lsbdecode)
        - [LSB().encode](#lsbencode)
        - [LSB().getLsb](#lsbgetlsb)
        - [LSB().getLsb8](#lsbgetlsb8)
        - [LSB().getLsb8C](#lsbgetlsb8c)
        - [LSB().setLsb](#lsbsetlsb)
        - [LSB().setLsb8](#lsbsetlsb8)
        - [LSB().setLsb8C](#lsbsetlsb8c)
        - [LSB().simpleDecode](#lsbsimpledecode)
        - [LSB().simpleEncode](#lsbsimpleencode)

## LSB

[[find in source code]](../../stegstash/lsb.py#L5)

```python
class LSB():
    def __init__(array, pointer=0, data=None):
```

Perform lsb encoding and decoding on an array

### LSB().decode

[[find in source code]](../../stegstash/lsb.py#L83)

```python
def decode(mapSeed, password='', zeroTerm=True, file=None):
```

decode data from an array using lsb steganography

#### Arguments

- `mapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".
- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.

#### Returns

- `bytes` - data from the image

### LSB().encode

[[find in source code]](../../stegstash/lsb.py#L113)

```python
def encode(mapSeed, password=''):
```

encode an array with data using lsb steganography

#### Arguments

- `mapSeed` *string* - seed to generate the lsb map
- `password` *str, optional* - password to encrypt the data with. Defaults to "".

### LSB().getLsb

[[find in source code]](../../stegstash/lsb.py#L22)

```python
def getLsb():
```

get lsb

### LSB().getLsb8

[[find in source code]](../../stegstash/lsb.py#L37)

```python
def getLsb8():
```

get lsb8

### LSB().getLsb8C

[[find in source code]](../../stegstash/lsb.py#L50)

```python
def getLsb8C():
```

get lsb8 char

### LSB().setLsb

[[find in source code]](../../stegstash/lsb.py#L14)

```python
def setLsb(bit):
```

set lsb

### LSB().setLsb8

[[find in source code]](../../stegstash/lsb.py#L31)

```python
def setLsb8(byte):
```

set lsb8

### LSB().setLsb8C

[[find in source code]](../../stegstash/lsb.py#L45)

```python
def setLsb8C(char):
```

set lsb8 char

### LSB().simpleDecode

[[find in source code]](../../stegstash/lsb.py#L56)

```python
def simpleDecode(zeroTerm=True, file=None):
```

decode a flat array with no encryption

#### Arguments

- `zeroTerm` *boolean, optional* - stop decoding on   (NUL). Defaults to True.
- `file` *<file>, optional* - file pointer. Defaults to None.

### LSB().simpleEncode

[[find in source code]](../../stegstash/lsb.py#L73)

```python
def simpleEncode():
```

encode a flat array with no encryption
