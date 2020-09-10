# Filter bwa results and output additional stats

## What it does

This extension works with the output files from the mapping rules.
It will filter the alignments based on an alignment length and percent identity threshold.
It will also output:
1) Coverage stats for the filtered alignments
2) Number of reads aligned to each segment for both filtered and non-filtered alignments. From the samtools idxstats man page: "the output is TAB-delimited with each line consisting of reference sequence name, sequence length, # mapped read-segments and # unmapped read-segments".
3) Calculate mean coverage in a sliding window across segments for both filtered and non-filtered alignments. The window size parameter is the width of the section to calculate the mean coverage. The sampling parameter determines at which nucleotide the output should be written. The mean coverage will be output at every nth nucleotide. Also the segments less than the sampling size will not be outputted at all.

## Install (legacy instructions for sunbeam <3.0)
 
 With your [sunbeam](https://github.com/sunbeam-labs/sunbeam) conda environment activated, 
 
 1. Clone into your Sunbeam directory:
 
  ```bash
  https://github.com/ctanes/sbx_mapping_withFilter.git
  ```
 
 2. Add the new config options to your config file
 
  ```bash
  cat sunbeam/extensions/sbx_mapping_withFilter/config.yml >> sunbeam_config.yml
  ```
