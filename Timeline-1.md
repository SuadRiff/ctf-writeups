# CTF Write-up: Timeline 1 (Forensics)

## Overview
This challenge involves the forensic analysis of a disk image to recover a hidden flag.

## Strategy
* **Timeline Creation**: Used SleuthKit to track file system modifications.
* **Temporal Correlation**: Analyzed timestamps near anti-forensic actions.
* **Data Filtering**: Used grep to isolate relevant artifacts.

## Solving Steps
### 1. Decompression
`gunzip partition4.img.gz`

### 2. Timeline Analysis
`fls -r -m / partition4.img > body.txt`
`mactime -b body.txt > timeline.txt`

### 3. Searching
Performed a directory-level sweep of /etc/. This revealed Inode 32716 as a high-priority artifact.

### 4. Extraction
`icat partition4.img 32716`

## Final Flag
picoCTF{573417h13r_7h4n_7h3_1457_58527bb222}
