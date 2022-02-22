# Trabalho realizado na Semana #3

## Identificação

- CVE-2021-3246- A  heap buffer overflow vulnerability in msadpcm_decode_block of libsndfile 1.0.30 allows attackers to execute arbitrary code via a crafted WAV file.


## Catalogação

- In 2021, Andrea Fioraldi discovered a buffer overflow in libsndfile, a library for reading/writing audio files. This flaw allows an attacker to execute arbitrary code via a crafted WAV file. The highest threat from this vulnerability is to confidentiality, integrity, as well as system availability. Its CVE score is 8.8 and it has a high impact.

## Exploit

- A heap buffer overflow vulnerability in msadpcm_decode_block of libsndfile 1.0.30 allows attackers to execute arbitrary code via a crafted WAV file.

## Ataques


- The attack could result in denial of service or potentially the execution of arbitrary code when processing a malformed audio file.
