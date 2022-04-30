See file [`INSTALL.md`](INSTALL.md).

Please read help:
```bash
build/grainofsalt --help
```

The program generates CNFs for stream ciphers. The cipher can easily be
changed or modified, see configuration files under 'build'. There are
a multitude of options. The most important ones are:
```
--crypto   : which cryptographic primitive is to be used
--outputs  : number of known output bits
--probBits : number probabilistic help bits given
              (needed to aid soving, otherwise it's too long)
--num      : number of CNF files to generate
--debug    : all help bits will be correct, so the resulting CNFs
             will all be SATisfiable
```
The descriptions of the cryptographic primitives are under their own di-
rectories, i.e. 'build/crypto1' or 'build/trivium'. You can make your own,
just define the feedback&filter functions, plus the output functions of the
cryptographic problem. You need to provide the ANF to these functions: each
line is a monomial, and each line is XOR-ed with each other to create the
final polynomial. For example, 'grain/functions/output.txt' describes the
output function of the cipher Grain. The notation used in these files are:
srX = shift regiser number X, fX = filter function number X. For example,
filter function number 0 is under 'grain/functions/f0.txt'

Example usage:

go to the `buid` directory, and issue:
```bash
./grainofsalt --xorclauses --debug --num 10 --crypto trivium --outputs 90 --probBits 70
```

Generates 10 problems into `build/satfiles`. These problems are based on the
Trivium cipher, with 90 bits of observed output, random key, random plaintext,
and 70 randomly given key bits, all bits set randomly to 0 or 1.

For more a complete HOWTO, please go to my website: just google "Mate Soos"
