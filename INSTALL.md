To compile, you will need:
* cmake
* bignum library (with development headers)
* boost library (with development headers)
* zlib library (with development headers)

Once these are installed, issue:
```bash
cd build
cmake ..
make
```

Please do NOT try to skip the `cd build`. Your build will succeed, but
it will not be usable.

To use, issue from directory `build`:
```bash
./grainofsalt --num 100 --outputs 90 --crypto grain
```
