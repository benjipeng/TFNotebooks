# Introducing Pickle
`Pickle in Python: Object Serialization`. `Pickle` serializes objects. Can be saved to a file, or loaded in again for later.
## Details in pickling
*aka `marshalling` or `flattening`.*

Serialization in `pickle` converts an object in memory to a `bytestream` (a sequence of bytes). 
>Pickling is useful for applications with persistency in data. Program's state data can be saved to disk and worked on later. Can be used when sending data over a Transmission Control Protocol (TCP), to store python objects in a database, and etc.  **Pickle is very useful with machine learning algorithms**.

The following datatypes can be pickled.
- [x] Booleans
- [x] Integers, Floats, Strings
- [x] Tuples, Lists, Sets, Dictionaries
- [ ] classes and functions 

## Pickle in action
### Pickling an object
starting with importing `pickle`, there is a `dict` with `{key : value}` pairing.

`open()` opens files for writing. First argument is file. In the second argument, flag `'w'` means write and `'b'` means binary mode.
```python
import pickle
dogs_dict = { 'Ozzy': 3, 'Filou': 8, 'Luna': 5, 'Skippy': 10, 'Barco': 12, 'Balou': 9, 'Laika': 16 }
filename = 'dogs' ## specify name
outfile = open(filename,'wb') ## w+b also works insead of 'wb'.
pickle.dump(dogs_dict,outfile)
outfile.close()
```

### Unpickling files
`'rb'` means `read`, `binary mode`.
```python
infile = open(filename,'rb')
new_dict = pickle.load(infile)
infile.close()
```
