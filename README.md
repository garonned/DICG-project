
# Usage
Source files are in `src/`
All sources are given computed as well (for c++) to avoid (c)make/dependancies issues. Pandas will still be required for python scripts. To install it, `sudo pip3 install pandas` and `sudo pip3 install pandas --upgrade` if there is still an issue.

Please note that scriptClassification.sh was slightly modified: a "$i" was added line 27 to know where we are in the tests.

## Invariants
To get the invariants of the image `beetle-1` just type `./src/invariants database/beetle-1.pgm`.
To create a `data.csv` containing the invariants of every examples of the database, execute script `./src/getInvar.sh > data.csv` (not recommended though, cf report)

## Preprocessing
This tool outputs different results of the preprocessing for the same image. Type `./src/preprocessing database/beetle-1.pgm`.

## Modified images
A database image can be modified in three ways : `imgRotate`, `imgScale`, `imgAddNoise`.
To test the classification of randomly modified images, type `zsh scriptClassification.sh`. The recognition works perfectly when Rank is 1.

## Distances
To show the `9` neighbors of a given image like `beetle-1`, do `python3 src/classification.py database/beetle-1.pgm 9 v`.
Removing `v` gives the probability of matching for each class of `classes.csv`.


# Similarity measure between two images

- values must be in [0,1]
- 1 means "similar"


# Classification evaluation

- the tool must output (standard output) a list of 70 values between 0
and 1 (classification score or probability to belong to the class)

- ```getRank``` returns the rank of a given class in a given
  classification score.
