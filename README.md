![Version](https://img.shields.io/github/v/release/DCMLab/cpe_bach_keyboard?display_name=tag)
[![DOI](https://zenodo.org/badge/649359237.svg)](https://doi.org/10.5281/zenodo.14996326)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/cpe_bach_keyboard)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/cpe_bach_keyboard](https://github.com/DCMLab/cpe_bach_keyboard) and the corresponding
* documentation page [https://dcmlab.github.io/cpe_bach_keyboard](https://dcmlab.github.io/cpe_bach_keyboard)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/cpe_bach_keyboard/introduction).

# Carl Philipp Emanuel Bach – Works for Keyboard (A corpus of annotated scores)


This corpus of annotated [MuseScore](https://musescore.org) files has been created within
the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora) and employs
the [DCML harmony annotation standard](https://github.com/DCMLab/standards).

The second surviving son of Johann Sebastian Bach, Carl Philipp Emanuel Bach charted his own course as an innovative
composer in the "Empfindsamer Stil" (Sentimental Style) on the cusp of Baroque and Classical practice, and for a time,
his fame surpassed his father's. Emanuel Bach's style is characterized by rapid, urgent, and often shocking
juxtapositions of mood within a single movement; it is not hard to see why this music held a particular influence on a
young Ludwig van Beethoven. This repository reflects a selection both of longer sonatas and rondos (including both
single-movement and multi-movement sonatas) and of freeform Fantasias in order to reflect a cross-section of this
composer's unique practice. 
 
Wq. 50 is a didactic group of "Sonaten mit veränderten Reprisen" (Sonatas with Varied Reprises) intended to instruct
the performer in the proper method of ornamenting a repeated section. Wq. 55 through 57 come from Bach's "Kenner und
Liebhaber" (Connoisseurs and Amateurs) series, whose wide circulation Bach supervised himself, and whose title is
somewhat ironic given the virtuosity on showcase in these works. The remaining pieces in this repository are a
selection of Free Fantasias, all of which are found in volumes that combine keyboard works in a variety of genres,
such as Wq. 112, "Clavierstücke verschiedener Art" (Piano Pieces of Various Kinds). These Fantasias -- which, as 
their name implies, are not bound by formal conventions -- are themselves divided between concise etude-like
miniatures like Wq. 113/3 and extended unmeasured soliloquies like Wq. 117/13. 
 
These scores were typeset especially for this project by Anna Yuferova following the critical editions from the
Packard Institute, with the exception of Wq. 117/12 and 55/4, which were downloaded from the MuseScore catalogue.


## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/cpe_bach_keyboard/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [cpe_bach_keyboard.zip](https://github.com/DCMLab/cpe_bach_keyboard/releases/latest/download/cpe_bach_keyboard.zip)
  * [cpe_bach_keyboard.datapackage.json](https://github.com/DCMLab/cpe_bach_keyboard/releases/latest/download/cpe_bach_keyboard.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/cpe_bach_keyboard.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first movement of the *Sonata in F Major*, Wq.50/1, has the following files:

* `MS3/wq50n01a.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/wq50n01a.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/wq50n01a.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/wq50n01a.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/wq50n01a.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10 or later) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/wq50n01a.harmonies.tsv")
notes = ms3.load_tsv("notes/wq50n01a.notes.tsv")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/cpe_bach_keyboard/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/cpe_bach_keyboard/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Johannes Hentschel, Yannis Rammos, Markus Neuwirth, & Martin Rohrmeier. (2025). Carl Philipp Emanuel Bach – Works for Keyboard (A corpus of annotated scores) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.14996326

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## File naming convention

```regex
wq(?<wotquenne>\d{2,3})
n(?<no>\d{2})
(?<movement>[a-c])?
```

## Overview
|file_name|measures|labels|standard| annotators  |    reviewers     |
|---------|-------:|-----:|--------|-------------|------------------|
|wq112n02 |      19|    38|2.3.0   |Amelia Brey  |DK                |
|wq112n08 |      12|    56|2.3.0   |Amelia Brey  |DK                |
|wq112n15 |      13|    28|2.3.0   |Amelia Brey  |DK                |
|wq113n03 |       7|    29|2.3.0   |Amelia Brey  |DK                |
|wq114n07 |       4|    45|2.3.0   |Victor Zheng |Johannes Hentschel|
|wq117n11 |      14|    35|2.3.0   |Amelia Brey  |DK                |
|wq117n12 |      14|    21|2.3.0   |Amelia Brey  |DK                |
|wq117n13 |       3|    86|2.3.0   |Amelia Brey  |Johannes Hentschel|
|wq117n14 |      26|    36|2.3.0   |Davor Krkljus|AB                |
|wq119n07 |     123|   340|2.3.0   |Amelia Brey  |DK                |
|wq50n01a |      48|   216|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq50n01b |      25|    42|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq50n01c |     166|   244|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq50n02a |     192|   340|2.3.0   |Davor Krkljus|ST                |
|wq50n02b |      31|    91|2.3.0   |Davor Krkljus|ST                |
|wq50n02c |     133|   215|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq50n03a |     192|   280|2.3.0   |Davor Krkljus|AB                |
|wq50n03b |      41|    88|2.3.0   |Davor Krkljus|AB                |
|wq50n03c |     100|   165|2.3.0   |Davor Krkljus|AB                |
|wq50n04a |     156|   329|2.3.0   |Victor Zheng |DK                |
|wq50n04b |      17|    73|2.3.0   |Victor Zheng |DK                |
|wq50n04c |     131|   333|2.3.0   |Victor Zheng |DK                |
|wq50n05a |     104|   386|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq50n05b |      60|   114|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq50n05c |     229|   390|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq50n06  |     234|   450|2.3.0   |Davor Krkljus|AB                |
|wq55n01a |      69|    95|2.3.0   |Amelia Brey  |DK                |
|wq55n01b |      39|    58|2.3.0   |Amelia Brey  |DK                |
|wq55n01c |      44|    78|2.3.0   |Amelia Brey  |DK                |
|wq55n02a |      77|   167|2.3.0   |Amelia Brey  |DK                |
|wq55n02b |      49|   116|2.3.0   |Amelia Brey  |DK                |
|wq55n02c |     160|   163|2.3.0   |Amelia Brey  |DK                |
|wq55n03a |      42|    89|2.3.0   |Amelia Brey  |DK                |
|wq55n03b |      25|    41|2.3.0   |Amelia Brey  |DK                |
|wq55n03c |      68|   147|2.3.0   |Amelia Brey  |DK                |
|wq55n04a |     128|   314|2.3.0   |Davor Krkljus|AB                |
|wq55n04b |      32|   121|2.3.0   |Davor Krkljus|AB                |
|wq55n04c |     135|   266|2.3.0   |Davor Krkljus|AB                |
|wq55n05a |      29|   102|2.3.0   |Amelia Brey  |DK                |
|wq55n05b |      30|    64|2.3.0   |Amelia Brey  |DK                |
|wq55n05c |      37|    70|2.3.0   |Amelia Brey  |DK                |
|wq55n06a |      66|   229|2.3.0   |Davor Krkljus|AB                |
|wq55n06b |      30|    89|2.3.0   |Davor Krkljus|AB                |
|wq55n06c |     122|   202|2.3.0   |Davor Krkljus|AB                |
|wq56n01  |     176|   435|2.3.0   |Davor Krkljus|AB                |
|wq56n02a |      71|   164|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq56n02b |      24|    58|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq56n02c |      48|   115|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq56n03  |     149|   425|2.3.0   |Davor Krkljus|AB                |
|wq56n04a |      47|   161|2.3.0   |Davor Krkljus|AB                |
|wq56n04b |      73|   101|2.3.0   |Davor Krkljus|AB                |
|wq56n05  |     172|   308|2.3.0   |Davor Krkljus|AB                |
|wq56n06a |      41|    83|2.3.0   |Amelia Brey  |DK                |
|wq56n06b |      52|    90|2.3.0   |Amelia Brey  |DK                |
|wq57n01  |      94|   557|2.3.0   |Davor Krkljus|AB                |
|wq57n02a |      41|   116|2.3.0   |Amelia Brey  |DK                |
|wq57n02b |      32|    68|2.3.0   |Amelia Brey  |DK                |
|wq57n02c |      58|   139|2.3.0   |Victor Zheng |DK                |
|wq57n03  |     141|   283|2.3.0   |Davor Krkljus|AB                |
|wq57n04a |      81|   175|2.3.0   |Davor Krkljus|AB                |
|wq57n04b |      73|   166|2.3.0   |Davor Krkljus|AB                |
|wq57n04c |      52|    98|2.3.0   |Davor Krkljus|AB                |
|wq57n05  |     224|   366|2.3.0   |Davor Krkljus|AB                |
|wq57n06a |      90|   161|2.3.0   |Davor Krkljus|                  |
|wq57n06b |      44|   106|2.3.0   |Davor Krkljus|Victor Zheng      |
|wq57n06c |      70|   135|2.3.0   |Davor Krkljus|Victor Zheng      |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
