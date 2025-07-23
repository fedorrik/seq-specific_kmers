# kmerer

Get cenhap specific kmers from the set of centromere assemblies

### Specifisity rules: 
- `target` kmer has more than 30 hits in a given assembly
- `background` kmer has less than 10% (of target hit counts) hits in assemblies of other cenhaps

### Dependencies:
- jellifish

### Run:
- `./count_all_kmers.sh --dir-with-fastas <seq_dir> --kmer-length <kmer_length>`
- <seq_dir> must contain centromere sequences (full chromosomes are too long) with cenhap assignment at the and of name after "_". Sequnces with the same cenhap won't be used as negative control to each other. If there is no cenhap assignments (no "_"), all sequences would be a negative control to all.

### to_xlsx script:
- collect all the cnt file from `kmers_specific_cnt` dir to one xlsx file
- Requiers `openpyxl` and `xlsxwriter` pip libraries 
- `python3 to_xlsx.py <path/to/kmer_counts> <output>.xlsx`

