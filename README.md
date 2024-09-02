# How to create a Singularity container with DNABERT2 and Triton

Do:

```bash
./create.sh 
```

## Output

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

## Files used by continuous integration scripts

Filename                              |Descriptions
--------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------
[mlc_config.json](mlc_config.json)    |Configuration of the link checker, use `markdown-link-check --config mlc_config.json --quiet docs/**/*.md` to do link checking locally
[.spellcheck.yml](.spellcheck.yml)    |Configuration of the spell checker, use `pyspelling -c .spellcheck.yml` to do spellcheck locally
[.wordlist.txt](.wordlist.txt)        |Whitelisted words for the spell checker, use `pyspelling -c .spellcheck.yml` to do spellcheck locally
[.markdownlint.jsonc](.markdownlint.jsonc)|Configuration of the markdown linter, use `markdownlint "**/*.md"` to do markdown linting locally. The name of this file is a default name.
[.markdownlintignore](.markdownlintignore)|Files ignored by the markdown linter, use `markdownlint "**/*.md"` to do markdown linting locally. The name of this file is a default name.
