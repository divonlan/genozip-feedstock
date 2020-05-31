genozip
=======

\
 **genozip** is a compressor for genomic files - it compresses VCF/BCF,
SAM/BAM, fastq, fasta, GVF and 23andMe files. If can even compress them
if they are already compressed with .gz .bz2 .xz (for full list of
supported file types see 'genozip --input --help').\
 \
 It achieves x2 to x5 better compression ratios than gzip because it
leverages some properties specific to genomic data to compress better.
It is also a lot faster than gzip.\
 \
 The compression is lossless - the decompressed file is 100% identical
to the original file.\
 \
 The command line options are similar to gzip and bcftools, so if you're
familiar with these, it works pretty much the same. To get started, try:
**genozip** --help\
 \
 ***Commands***: \
 **genozip** - compress one or more files \
 **genounzip** - decompress one or more files \
 **genols** - show metadata of one or more files or the entire directory
\
 **genocat** - view one or more files \
 \
 ***Some advanced options:***\
 \
 ***Lookups:***\
 **genocat** -r \^Y,MT *file1.vcf* -- displays all chromosomes except Y
and MT\
 **genocat** -r -10000 *file1.vcf* -- displays positions up to 10000\
 **genocat** -s SMPL1,SMPL2 *file1.vcf* -- displays 2 samples\
 Note: there is no need for a separate indexing step or index file\
 \
 ***Concatenating & splitting:***\
 **genozip** *file1.vcf file2.vcf* -o *concat.vcf.genozip* \
 **genounzip** *concat.vcf.genozip* -O \
 \
 ***Calculating the MD5:***\
 **genozip** *file.vcf* --md5 \
 \
 ***Encryption:***\
 **genozip** *file.vcf* --password *abc* \
 \
 ***Even better compression, with some minor modifications of the
data:***\
 **genozip** *file.vcf* --optimize \
 \
 ***Compress and then verify that the compressed file decompresses
correctly:***\
 **genozip** *file.vcf* --test \
 \
 Do you find genozip to be helpful in your research? Please be so kind
as to support continued development by citing **Citing:**
https://doi.org/10.1093/bioinformatics/btaa290 \
 Feature requests and bug reports: **bugs@genozip.com** \
 \
 **genozip** is free for non-commercial use. For a commercial license,
please contact **sales@genozip.com** \
 \
 Usage is subject to terms and conditions. The non-commercial license
can be viewed with **genozip** --license\
 \
 THIS SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE AND
NON-INFRINGEMENT. IN NO EVENT SHALL THE COPYRIGHT HOLDERS OR ANYONE
DISTRIBUTING THE SOFTWARE BE LIABLE FOR ANY DAMAGES OR OTHER LIABILITY,
WHETHER IN CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.\


Current build status
====================


<table>

  <tr>
    <td>Azure</td>
    <td>
      <details>
        <summary>
          <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=8867&branchName=master">
            <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/genozip-feedstock?branchName=master">
          </a>
        </summary>
        <table>
          <thead><tr><th>Variant</th><th>Status</th></tr></thead>
          <tbody><tr>
              <td>linux</td>
              <td>
                <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=8867&branchName=master">
                  <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/genozip-feedstock?branchName=master&jobName=linux&configuration=linux_" alt="variant">
                </a>
              </td>
            </tr><tr>
              <td>osx</td>
              <td>
                <a href="https://dev.azure.com/conda-forge/feedstock-builds/_build/latest?definitionId=8867&branchName=master">
                  <img src="https://dev.azure.com/conda-forge/feedstock-builds/_apis/build/status/genozip-feedstock?branchName=master&jobName=osx&configuration=osx_" alt="variant">
                </a>
              </td>
            </tr>
          </tbody>
        </table>
      </details>
    </td>
  </tr>
  <tr>
    <td>Windows</td>
    <td>
      <img src="https://img.shields.io/badge/Windows-disabled-lightgrey.svg" alt="Windows disabled">
    </td>
  </tr>
  <tr>
    <td>Linux_ppc64le</td>
    <td>
      <img src="https://img.shields.io/badge/ppc64le-disabled-lightgrey.svg" alt="ppc64le disabled">
    </td>
  </tr>
</table>

Current release info
====================

| Name | Downloads | Version | Platforms |
| --- | --- | --- | --- |
| [![Conda Recipe](https://img.shields.io/badge/recipe-genozip-green.svg)](https://anaconda.org/conda-forge/genozip) | [![Conda Downloads](https://img.shields.io/conda/dn/conda-forge/genozip.svg)](https://anaconda.org/conda-forge/genozip) | [![Conda Version](https://img.shields.io/conda/vn/conda-forge/genozip.svg)](https://anaconda.org/conda-forge/genozip) | [![Conda Platforms](https://img.shields.io/conda/pn/conda-forge/genozip.svg)](https://anaconda.org/conda-forge/genozip) |

Installing genozip
==================

Installing `genozip` from the `conda-forge` channel can be achieved by adding `conda-forge` to your channels with:

```
conda config --add channels conda-forge
```

Once the `conda-forge` channel has been enabled, `genozip` can be installed with:

```
conda install genozip
```

It is possible to list all of the versions of `genozip` available on your platform with:

```
conda search genozip --channel conda-forge
```


About conda-forge
=================

[![Powered by NumFOCUS](https://img.shields.io/badge/powered%20by-NumFOCUS-orange.svg?style=flat&colorA=E1523D&colorB=007D8A)](http://numfocus.org)

conda-forge is a community-led conda channel of installable packages.
In order to provide high-quality builds, the process has been automated into the
conda-forge GitHub organization. The conda-forge organization contains one repository
for each of the installable packages. Such a repository is known as a *feedstock*.

A feedstock is made up of a conda recipe (the instructions on what and how to build
the package) and the necessary configurations for automatic building using freely
available continuous integration services. Thanks to the awesome service provided by
[CircleCI](https://circleci.com/), [AppVeyor](https://www.appveyor.com/)
and [TravisCI](https://travis-ci.com/) it is possible to build and upload installable
packages to the [conda-forge](https://anaconda.org/conda-forge)
[Anaconda-Cloud](https://anaconda.org/) channel for Linux, Windows and OSX respectively.

To manage the continuous integration and simplify feedstock maintenance
[conda-smithy](https://github.com/conda-forge/conda-smithy) has been developed.
Using the ``conda-forge.yml`` within this repository, it is possible to re-render all of
this feedstock's supporting files (e.g. the CI configuration files) with ``conda smithy rerender``.

For more information please check the [conda-forge documentation](https://conda-forge.org/docs/).

Terminology
===========

**feedstock** - the conda recipe (raw material), supporting scripts and CI configuration.

**conda-smithy** - the tool which helps orchestrate the feedstock.
                   Its primary use is in the construction of the CI ``.yml`` files
                   and simplify the management of *many* feedstocks.

**conda-forge** - the place where the feedstock and smithy live and work to
                  produce the finished article (built conda distributions)


Updating genozip-feedstock
==========================

If you would like to improve the genozip recipe or build a new
package version, please fork this repository and submit a PR. Upon submission,
your changes will be run on the appropriate platforms to give the reviewer an
opportunity to confirm that the changes result in a successful build. Once
merged, the recipe will be re-built and uploaded automatically to the
`conda-forge` channel, whereupon the built conda packages will be available for
everybody to install and use from the `conda-forge` channel.
Note that all branches in the conda-forge/genozip-feedstock are
immediately built and any created packages are uploaded, so PRs should be based
on branches in forks and branches in the main repository should only be used to
build distinct package versions.

In order to produce a uniquely identifiable distribution:
 * If the version of a package **is not** being increased, please add or increase
   the [``build/number``](https://conda.io/docs/user-guide/tasks/build-packages/define-metadata.html#build-number-and-string).
 * If the version of a package **is** being increased, please remember to return
   the [``build/number``](https://conda.io/docs/user-guide/tasks/build-packages/define-metadata.html#build-number-and-string)
   back to 0.

Feedstock Maintainers
=====================

* [@divonlan](https://github.com/divonlan/ divon@genozip.com)
