stuff for creating a rust crate for the microcontroller, from an SVD file

The .atpack was obtained from https://packs.download.microchip.com/ and can be unzipped with 7z.

However I'm having some trouble converting this using svd2rust:

```
svd2rust -i extracted/svd/ATSAML22G18A.svd
[INFO  svd2rust] Parsing device from SVD file
[ERROR svd2rust] Error parsing SVD XML file

    Caused by:
        0: In device `ATSAML22G18A`
        1: In peripheral `GCLK`
        2: In register `SYNCBUSY`
        3: Parsing field `GENCTRL0` at 5635:19
        4: `EnumeratedValue error: Value 2 out of range 0..2
```

According to this tweet, svg2rust can be used though, if a few tweaks are made to the svd file. https://twitter.com/josecastillo/status/1484522506203631627

See also https://github.com/rust-embedded/svd2rust/issues/559
