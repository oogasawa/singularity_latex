# singularity_latex

A singularity container of LaTeX typesetting system.

## Usage

Build the Singularity image as follows:

```
git clone https://github.com/oogasawa/singularity_latex
cd singularity_latex
sudo singularity build singularity_latex.sif Singularity
```


Compile a LaTeX file. (a DVI file will be generated.)

```
singularity exec singularity_latex.sif platex doc.tex
```


Generate a PDF file from a DVI file.

```
singularity exec singularity_latex.sif dvipdfmx doc.dvi
```

