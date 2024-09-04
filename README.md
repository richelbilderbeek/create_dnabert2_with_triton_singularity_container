# How to create a Singularity container with DNABERT2 and Triton

This script creates a Singularity container with DNABERT2 and Triton.

- DNABERT 2: [https://github.com/MAGICS-LAB/DNABERT_2](https://github.com/MAGICS-LAB/DNABERT_2)
- Triton: [https://github.com/triton-lang/triton](https://github.com/triton-lang/triton)

## Building the container

Do:

```bash
./create.sh 
```

Output will be similar to:

```bash
richel@richel-N141CU:~/GitHubs/ticket_297538$ time ./create.sh 
[sudo] password for richel: 
INFO:    Starting build...
INFO:    Fetching OCI image...
119.3MiB / 119.3MiB [================================================================================================================================================] 100 % 0.0 b/s 0s
26.2MiB / 26.2MiB [==================================================================================================================================================] 100 % 0.0 b/s 0s
INFO:    Extracting OCI image...
INFO:    Inserting Singularity configuration...
INFO:    Running post scriptlet
[...]
INFO:    Adding environment to container
INFO:    Adding runscript
INFO:    Creating SIF file...
INFO:    Build complete: dnabert2_with_triton.sif

real 11m22.296s
user 0m0.169s
sys 0m0.466s
```

## Using the container

The container is made to run its `python3` on the script filename provided,
for example:

```bash
./dnabert2_with_triton.sif example_dnabert2_with_triton.py
```

Alternatively, one can use `singularity shell` to interact with
it as if it is a shell:

```bash
$ singularity shell dnabert2_with_triton.sif 
bash: warning: setlocale: LC_ALL: cannot change locale (en_US.utf-8)
Singularity> conda list
WARNING conda.gateways.disk.delete:unlink_or_rename_to_trash(182): Could not remove or rename /opt/conda/conda-meta/tqdm-4.66.2-pyhd8ed1ab_0.json.  Please remove this file manually (you may need to reboot to free file handles)
WARNING conda.gateways.disk.delete:unlink_or_rename_to_trash(182): Could not remove or rename /opt/conda/conda-meta/requests-2.31.0-pyhd8ed1ab_0.json.  Please remove this file manually (you may need to reboot to free file handles)
# packages in environment at /opt/conda:
#
# Name                    Version                   Build  Channel
_libgcc_mutex             0.1                 conda_forge    conda-forge
_openmp_mutex             4.5                       2_gnu    conda-forge
accelerate                0.34.0                   pypi_0    pypi
aiohappyeyeballs          2.4.0                    pypi_0    pypi
aiohttp                   3.10.5                   pypi_0    pypi
aiosignal                 1.3.1                    pypi_0    pypi
antlr4-python3-runtime    4.9.3                    pypi_0    pypi
archspec                  0.2.3              pyhd8ed1ab_0    conda-forge
async-timeout             4.0.3                    pypi_0    pypi
attrs                     24.2.0                   pypi_0    pypi
boltons                   24.0.0             pyhd8ed1ab_0    conda-forge
brotli-python             1.1.0           py310hc6cd4ac_1    conda-forge
bzip2                     1.0.8                hd590300_5    conda-forge
c-ares                    1.28.1               hd590300_0    conda-forge
ca-certificates           2024.2.2             hbcca054_0    conda-forge
certifi                   2024.2.2           pyhd8ed1ab_0    conda-forge
cffi                      1.16.0          py310h2fee648_0    conda-forge
charset-normalizer        3.3.2              pyhd8ed1ab_0    conda-forge
cmake                     3.30.2                   pypi_0    pypi
colorama                  0.4.6              pyhd8ed1ab_0    conda-forge
conda                     24.3.0          py310hff52083_0    conda-forge
conda-libmamba-solver     24.1.0             pyhd8ed1ab_0    conda-forge
conda-package-handling    2.2.0              pyh38be061_0    conda-forge
conda-package-streaming   0.9.0              pyhd8ed1ab_0    conda-forge
datasets                  2.21.0                   pypi_0    pypi
dill                      0.3.8                    pypi_0    pypi
distro                    1.9.0              pyhd8ed1ab_0    conda-forge
einops                    0.8.0                    pypi_0    pypi
evaluate                  0.4.2                    pypi_0    pypi
filelock                  3.15.4                   pypi_0    pypi
fmt                       10.2.1               h00ab1b0_0    conda-forge
frozenlist                1.4.1                    pypi_0    pypi
fsspec                    2024.6.1                 pypi_0    pypi
huggingface-hub           0.24.6                   pypi_0    pypi
icu                       73.2                 h59595ed_0    conda-forge
idna                      3.6                pyhd8ed1ab_0    conda-forge
jinja2                    3.1.4                    pypi_0    pypi
jsonpatch                 1.33               pyhd8ed1ab_0    conda-forge
jsonpointer               2.4             py310hff52083_3    conda-forge
keyutils                  1.6.1                h166bdaf_0    conda-forge
krb5                      1.21.2               h659d440_0    conda-forge
ld_impl_linux-64          2.40                 h41732ed_0    conda-forge
libarchive                3.7.2                h2aa1ff5_1    conda-forge
libcurl                   8.7.1                hca28451_0    conda-forge
libedit                   3.1.20191231         he28a2e2_2    conda-forge
libev                     4.33                 hd590300_2    conda-forge
libffi                    3.4.2                h7f98852_5    conda-forge
libgcc-ng                 13.2.0               h807b86a_5    conda-forge
libgomp                   13.2.0               h807b86a_5    conda-forge
libiconv                  1.17                 hd590300_2    conda-forge
libmamba                  1.5.8                had39da4_0    conda-forge
libmambapy                1.5.8           py310h39ff949_0    conda-forge
libnghttp2                1.58.0               h47da74e_1    conda-forge
libnsl                    2.0.1                hd590300_0    conda-forge
libsolv                   0.7.28               hfc55251_2    conda-forge
libsqlite                 3.45.2               h2797004_0    conda-forge
libssh2                   1.11.0               h0841786_0    conda-forge
libstdcxx-ng              13.2.0               h7e041cc_5    conda-forge
libuuid                   2.38.1               h0b41bf4_0    conda-forge
libxcrypt                 4.4.36               hd590300_1    conda-forge
libxml2                   2.12.6               h232c23b_1    conda-forge
libzlib                   1.2.13               hd590300_5    conda-forge
lz4-c                     1.9.4                hcb278e6_0    conda-forge
lzo                       2.10              h516909a_1000    conda-forge
mamba                     1.5.8           py310h51d5547_0    conda-forge
markupsafe                2.1.5                    pypi_0    pypi
menuinst                  2.0.2           py310hff52083_0    conda-forge
mpmath                    1.3.0                    pypi_0    pypi
multidict                 6.0.5                    pypi_0    pypi
multiprocess              0.70.16                  pypi_0    pypi
ncurses                   6.4.20240210         h59595ed_0    conda-forge
networkx                  3.3                      pypi_0    pypi
numpy                     2.1.1                    pypi_0    pypi
nvidia-cublas-cu12        12.1.3.1                 pypi_0    pypi
nvidia-cuda-cupti-cu12    12.1.105                 pypi_0    pypi
nvidia-cuda-nvrtc-cu12    12.1.105                 pypi_0    pypi
nvidia-cuda-runtime-cu12  12.1.105                 pypi_0    pypi
nvidia-cudnn-cu12         9.1.0.70                 pypi_0    pypi
nvidia-cufft-cu12         11.0.2.54                pypi_0    pypi
nvidia-curand-cu12        10.3.2.106               pypi_0    pypi
nvidia-cusolver-cu12      11.4.5.107               pypi_0    pypi
nvidia-cusparse-cu12      12.1.0.106               pypi_0    pypi
nvidia-nccl-cu12          2.20.5                   pypi_0    pypi
nvidia-nvjitlink-cu12     12.6.68                  pypi_0    pypi
nvidia-nvtx-cu12          12.1.105                 pypi_0    pypi
omegaconf                 2.3.0                    pypi_0    pypi
openssl                   3.2.1                hd590300_1    conda-forge
packaging                 24.0               pyhd8ed1ab_0    conda-forge
pandas                    2.2.2                    pypi_0    pypi
peft                      0.12.0                   pypi_0    pypi
pip                       24.0               pyhd8ed1ab_0    conda-forge
platformdirs              4.2.0              pyhd8ed1ab_0    conda-forge
pluggy                    1.4.0              pyhd8ed1ab_0    conda-forge
psutil                    6.0.0                    pypi_0    pypi
pyarrow                   17.0.0                   pypi_0    pypi
pybind11-abi              4                    hd8ed1ab_3    conda-forge
pycosat                   0.6.6           py310h2372a71_0    conda-forge
pycparser                 2.22               pyhd8ed1ab_0    conda-forge
pysocks                   1.7.1              pyha2e5f31_6    conda-forge
python                    3.10.14         hd12c33a_0_cpython    conda-forge
python-dateutil           2.9.0.post0              pypi_0    pypi
python_abi                3.10                    4_cp310    conda-forge
pytz                      2024.1                   pypi_0    pypi
pyyaml                    6.0.2                    pypi_0    pypi
readline                  8.2                  h8228510_1    conda-forge
regex                     2024.7.24                pypi_0    pypi
reproc                    14.2.4.post0         hd590300_1    conda-forge
reproc-cpp                14.2.4.post0         h59595ed_1    conda-forge
requests                  2.32.3                   pypi_0    pypi
ruamel.yaml               0.18.6          py310h2372a71_0    conda-forge
ruamel.yaml.clib          0.2.8           py310h2372a71_0    conda-forge
safetensors               0.4.4                    pypi_0    pypi
setuptools                69.5.1             pyhd8ed1ab_0    conda-forge
six                       1.16.0                   pypi_0    pypi
sympy                     1.13.2                   pypi_0    pypi
tk                        8.6.13          noxft_h4845f30_101    conda-forge
tokenizers                0.13.3                   pypi_0    pypi
torch                     2.4.0                    pypi_0    pypi
tqdm                      4.66.5                   pypi_0    pypi
transformers              4.29.2                   pypi_0    pypi
triton                    3.0.0                    pypi_0    pypi
truststore                0.8.0              pyhd8ed1ab_0    conda-forge
typing-extensions         4.12.2                   pypi_0    pypi
tzdata                    2024.1                   pypi_0    pypi
urllib3                   2.2.1              pyhd8ed1ab_0    conda-forge
wheel                     0.43.0             pyhd8ed1ab_1    conda-forge
xxhash                    3.5.0                    pypi_0    pypi
xz                        5.2.6                h166bdaf_0    conda-forge
yaml-cpp                  0.8.0                h59595ed_0    conda-forge
yarl                      1.9.7                    pypi_0    pypi
zstandard                 0.22.0          py310h1275a96_0    conda-forge
zstd                      1.5.5                hfc55251_0    conda-forge
```

## Files used by continuous integration scripts

Filename                              |Descriptions
--------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------
[mlc_config.json](mlc_config.json)    |Configuration of the link checker, use `markdown-link-check --config mlc_config.json --quiet docs/**/*.md` to do link checking locally
[.spellcheck.yml](.spellcheck.yml)    |Configuration of the spell checker, use `pyspelling -c .spellcheck.yml` to do spellcheck locally
[.wordlist.txt](.wordlist.txt)        |Whitelisted words for the spell checker, use `pyspelling -c .spellcheck.yml` to do spellcheck locally
[.markdownlint.jsonc](.markdownlint.jsonc)|Configuration of the markdown linter, use `markdownlint "**/*.md"` to do markdown linting locally. The name of this file is a default name.
[.markdownlintignore](.markdownlintignore)|Files ignored by the markdown linter, use `markdownlint "**/*.md"` to do markdown linting locally. The name of this file is a default name.
