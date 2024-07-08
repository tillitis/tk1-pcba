# TK1 PCBA

This repository contains the PCB design and manufacturing files for
the flexible Open Source security key, TKey (TK1).

This is part of a larger project that includes firmware and FPGA
designs, which are housed at
[tillitis-key1](https://github.com/tillitis/tillitis-key1).

For more general information about the TKey see,
- [www.tillitis.se](https://tillitis.se)
- [shop.tillitis.se](https://shop.tillitis.se)
- [TKey Developer Handbook](https://dev.tillitis.se/)


## Repository Contents
- KiCad project files for
    - tk1, under hw
    - mta1-usb-v1, under prototypes
    - mta1-usb-dev, under prototypes
- Manufacturing outputs (Gerber files, BOM, etc.), under [Github
  releases](https://github.com/tillitis/tk1-pcba/releases)
- Libraries, under hw/lib

The earlier version of TK1, such as the `mta1-usb-v1` and
`mta1-usb-dev`, that can be found under `prototypes/` are kept for
historical reasons. TK1 is the only version that is maintained and
developed.

## Getting started
1. Clone this repository:
2. Open the project file (`hw/tk1.kicad_pro`) in KiCad.

alternativly download a release to get the generated output (Gerber,
schematics etc.) to be viewed in your preferred tool.

## KiCad and tools
The project is built using KiCad version 7. Production files are built
in CI using KiBot, see the Makefile for exact version.

The KiBot flow can be run locally using the Make target

```
make run-kibot
```

the prerequisits are `Podman`. `Docker` can also be used, see the
Makefile for details.


## License
Unless otherwise noted, this project is licensed under CERN Open
Hardware License Version 2 - Strongly Reciprocal, see full license
under [LICENSE.txt](/LICENSE.txt).
```
Copyright Tillitis AB 2022-2024.

This source describes Open Hardware and is licensed under the CERN-OHL-S v2.

You may redistribute and modify this source and make products using it under
the terms of the CERN-OHL-S v2 (https://ohwr.org/cern_ohl_s_v2.txt).

This source is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY,
INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A
PARTICULAR PURPOSE. Please see the CERN-OHL-S v2 for applicable conditions.

Source location: https://github.com/tillitis/tk1-pcba

As per CERN-OHL-S v2 section 4, should You produce hardware based on this
source, You must where practicable maintain the Source Location visible
on the external case of the product or its packaging, and in its
documentation, even after modification.
```

The [CERN-OHL-S user guide](/User-guide-CERN-OHL-S.txt) is included to
make it easier to follow the license, both as a Licensor or a Licensee.

## History
This repo was created by filtering out relevant commits and files from
the [tillitis/tillits-key1](https://github.com/tillitis/tillitis-key1)
repo.

The filtering removed all files and commits that weren't related to
the tk1 hardware. This was done using
[git-filter-repo](https://github.com/newren/git-filter-repo).

To replicate the results up until commit `6c7629c` in this repo,
checkout commit `354aecb` in `tillitis/tillitis-key1` and run
`git-filter-repo --path hw/boards/mta1-library --path
hw/boards/mta1-usb-dev --path hw/boards/mta1-usb-v1 --path
hw/boards/tk1`.

All filtered commits have intact date, author, and code. Some
unrelated files are removed from some commits, but the commit messages
are left unchanged. Commit sha, tags and signatures are new. For
complete history, please see tillitis/tillitis-key1 from commit
`354aecb` and earlier.
