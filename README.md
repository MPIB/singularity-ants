# singularity-ants
[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/660)

Singularity recipes for base-images containing ANTs (Advanced Normalization Tools). You can get the [code and documentation for ANTs through GitHub](https://github.com/ANTsX/ANTs).

 - ANTs is pulled from its [github repository](https://github.com/ANTsX/ANTs) and build using cmake.
 - cmake and its dependencies are installed through the debian repositories via `apt-get install`.
 - At the end of the build process the image is cleaned up by:
    - removing cmake and its dependencies through `apt-get purge`,
    - deleting the package cache,
    - deleting the folder containing the cloned repository.
 - `$ANTSPATH` and `$PATH` are set according to the [compilation guide](https://github.com/ANTsX/ANTs/wiki/Compiling-ANTs-on-Linux-and-Mac-OS).
 - ANTs executable should therefore be directly available.
 - Successful build and `$PATH` setup is tested through calling antsRegistration with the -h flag.
