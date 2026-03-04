# seq-specific_kmers

Get specific kmers for the set of repeatative intput sequences (e.g. ASat arrays)

### Specifisity rules: 
- `target` kmer has more than 30 hits in a given sequence
- `background` kmer has less than 10% (of target hit counts) hits in any of other sequence (soft-threshold) or in sum count of other sequences (hard-threshold)

### Dependencies:
- jellifish

### Run:
- `./count_all_kmers.sh --dir-with-fastas <seq_dir> --kmer-length <kmer_length>`
- <seq_dir> must contain only input sequences. Sequences might be grouped by assignment at the and of name after "_". Sequnces with the same group won't be used as negative control (background) to each other. If there is no group assignments (no "_"), all sequences would be a negative control to all.
- Optional parameters
  - k, --kmer-length LENGTH K-mer length (default: 21)
  - r, --reverse-complement Count canonical k-mers (treat reverse complements as same, jellifish parameter)
  - ht, --hard-threshold    Apply hard threshold filter (default: soft-threshold)

### to_xlsx script:
- collect all the cnt file from `kmers_specific_cnt` dir to one xlsx file
- Requiers `openpyxl` and `xlsxwriter` pip libraries 
- `python3 to_xlsx.py <path/to/kmer_counts> <output>.xlsx`

