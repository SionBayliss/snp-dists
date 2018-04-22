[![Build Status](https://travis-ci.org/tseemann/snp-dists.svg?branch=master)](https://travis-ci.org/tseemann/snp-dists) [![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0) [](#lang-au)

# snpdist

Convert a FASTA alignment to SNP distance matrix

# Quick Start

```
% cat test/good.aln

>seq1
AGTCAGTC
>seq2
AGGCAGTC
>seq3
AGTGAGTA
>seq4
TGTTAGAC

% snp-dists test/good.aln > distances.tab

Read 4 sequences of length 8

% cat distances.tab

snp-dists 0.2   seq1    seq2    seq3    seq4
seq1            0       1       2       3
seq2            1       0       3       4
seq3            2       3       0       4
seq4            3       4       4       0
```

# Installation

`snp-dists` is written in C to the C99 standard and only depends on `zlib`.

## Source

```bash
git clone https://github.com/tseemann/snp-dists.git
cd snp-dists/src
make
# optionally install to /usr/local/bin 
make PREFIX=/usr/local install  
```

### Homebrew
```
brew install brewsci/bio/snp-dists
```

### Bioconda
```
conda install -c bioconda -c conda-forge snp-dists
```

# Options

## snp-dists -h (help)

```
SYNOPSIS
  Pairwise SNP distance matrix from a FASTA alignment
USAGE
  snp-dists [options] alignment.fasta > matrix.tsv
OPTIONS
  -h    Show this help
  -v    Print version and exit
  -q    Quiet mode; do not print progress information
  -c    Output CSV instead of TSV
  -b    Blank top left corner cell instead of 'snp-dists 0.2'
URL
  https://github.com/tseemann/snp-dists (Torsten Seemann)
```

## snp-dists -v (version)

Prints the name and version separated by a space in standard Unix fashion.

```
snp-dists 0.2
```

## snp-dists -q (quiet mode)

Don't print informational messages, only errors.

## snp-dists -c good.aln (CSV instead of TSV)

```
snp-dists 0.2,seq1,seq2,seq3,seq4
seq1,0,1,2,3
seq2,1,0,3,4
seq3,2,3,0,4
seq4,3,4,4,0
```

## snp-dists -b good.aln (Omit the toolname/version)

```
        seq1    seq2    seq3    seq4
seq1    0       1       2       3
seq2    1       0       3       4
seq3    2       3       0       4
seq4    3       4       4       0
```

# Issues

Report bugs and give suggesions on the
[Issues page](https://github.com/tseemann/snp-dists/issues)

# Licence

[GPL Version 3](https://raw.githubusercontent.com/tseemann/snp-dists/master/LICENSE)

# Author

[Torsten Seemann](https://tseemann.github.io)

