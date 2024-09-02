# How to create a Singularity container with DNABERT2 and Triton

Do:

```bash
./create.sh 
```

## Output

```
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

real	11m22.296s
user	0m0.169s
sys	0m0.466s
```
