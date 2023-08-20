# Fork of WireViz

## Summary

WireViz is a tool for easily documenting cables, wiring harnesses and connector pinouts.
It takes plain text, YAML-formatted files as input and produces beautiful graphical output (SVG, PNG, ...) thanks to [GraphViz](https://www.graphviz.org/).
It handles automatic BOM (Bill of Materials) creation and has a lot of extra features.

## Features

* WireViz input files are fully text based
  * No special editor required
  * Human readable
  * Easy version control
  * YAML syntax
  * UTF-8 input and output files for special character support
* Understands and uses color abbreviations as per [IEC 60757](https://en.wikipedia.org/wiki/Electronic_color_code#Color_band_system) (black=BK, red=RD, ...)
  <!-- * Optionally outputs colors as abbreviation (e.g. 'YE'), full name (e.g. 'yellow') or hex value (e.g. '#ffff00'), with choice of UPPER or lower case (#158) -->
* Auto-generates standard wire color schemes and allows custom ones if needed
  * [DIN 47100](https://en.wikipedia.org/wiki/DIN_47100) (WT/BN/GN/YE/GY/PK/BU/RD/BK/VT/...)
  * [IEC 60757](https://en.wikipedia.org/wiki/Electronic_color_code#Color_band_system)   (BN/RD/OR/YE/GN/BU/VT/GY/WT/BK/...)
  * [25 Pair Color Code](https://en.wikipedia.org/wiki/25-pair_color_code#Color_coding) (BUWH/WHBU/OGWH/WHOG/GNWH/WHGN/BNWH/...)
  * [TIA/EIA 568 A/B](https://en.wikipedia.org/wiki/TIA/EIA-568#Wiring)  (Subset of 25-Pair, used in CAT-5/6/...)
* Understands wire gauge in mm² or AWG
  * Optionally auto-calculates equivalent gauge between mm² and AWG
* Is suitable for both very simple cables, and more complex harnesses.
* Allows for easy-autorouting for 1-to-1 wiring
* Generates BOM (Bill of Materials)

_Note_: WireViz is not designed to represent the complete wiring of a system. Its main aim is to document the construction of individual wires and harnesses.

## Usage

### Installation

WireViz is available as a native binary on Linux AMD64 and ARM64 architecture: https://github.com/yuzutech/WireViz/releases.

### How to run

```
$ echo 'yaml definition' | wireviz -f svg - -o -
```

#### Command line options

- `--prepend-file <FILE>` to prepend an additional YAML file. Useful for part libraries and templates shared among multiple cables/harnesses.
- `-o <OUTPUT>` or `--output_file <OUTPUT>` to generate output files with a name different from the input file.
- `-V` or `--version` to display the WireViz version.
- `-h` or `--help` to see a summary of the usage help text.
- `-f` or `--format` to set the output format (supported formats: svg, png)

### Syntax description

A description of the WireViz YAML input syntax can be found [here](syntax.md).

## Changelog

See [CHANGELOG.md](CHANGELOG.md)

## License

[GPL-3.0](../LICENSE)
