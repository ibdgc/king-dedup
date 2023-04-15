# king-dedup

## Dependencies
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
- king-dedup coordinates inputs through a pre-configured comma separated sample file. This file should include:
    - A list of absolute paths to sequencing files
    - The genome reference used in preparation, indicated by a `0` or `1`
        - hg38 = `1`
        - hg19 = `0`
    - A header row should not be included

```sh
# Example samples.csv file
# This file should be placed in king-dedup/setup before execution
vim king-dedup/setup/samples.csv

/home/chris/plink/cedars/sample-set1.ped,0      # prepared with hg19
/home/chris/plink/broad/sample-set2.ped,0       # prepared with hg19
/home/chris/dbgap/sample-set3.bed,1             # prepared with hg38
```

## Usage
- Execution of king-dedup is performed with a single shell command.

```sh
cd king-dedup
./run
```

## Output
- The main routine will automatically generate a unique output directory.

