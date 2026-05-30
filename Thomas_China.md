# CTF Write-up: Thomas School of China

## Overview
Recovery of a hidden flag from a custom-formatted binary file (.tsc).

## Strategy
* **Header Verification**: Identified the non-standard TSCF header.
* **Obfuscation Analysis**: Investigated injected noise (kkktttu, CCCOOO, 666}).
* **Data Sanitization**: Cleaned the output to reveal the flag.

## Solving Steps
### 1. Signature Identification
Used `file` and `hexdump` to identify the non-standard header.

### 2. Artifact Extraction
Used `dd` to strip the header and expose the binary stream.

### 3. Sanitization
Filtered out the repeated junk patterns to recover the plaintext.

## Final Flag
tjctf{c0ngr4ts_u_s0lv3d_my_f1st_CTF_chall!_btw_1_l1ke_b1rds}
