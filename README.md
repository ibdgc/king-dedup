# king-dedup

## Dependencies
- snpflip for alignment to positive strand (https://github.com/biocore-ntnu/snpflip)
    - requires .bim file for each dataset and .fasta file for reference genome matching each input file
- Package management is handled by [conda](https://docs.conda.io/en/latest/miniconda.html).
- Tools installed during setup
    - `bcftools`
    - `picard`
    - `plink`
    - `plink2`
    - `king`


## Setup

### First Time
```sh
# clone the repo
git clone https://github.com/ibdgc/king-dedup.git
cd king-dedup
```

### Config
- king-dedup takes a single text file as an input. This file should included a list of absolute paths to sequencing files.

```sh
vim inputs.txt

/home/chris/plink/cedars/sample-set1.ped
/home/chris/plink/broad/sample-set2.ped
/home/chris/dbgap/sample-set3.bed
```

## Usage
- Execution of king-dedup is performed with a single shell command.

```sh
cd king-dedup
./run /path/to/inputs.txt
```

## Output
- The main routine will automatically generate a unique output directory.

