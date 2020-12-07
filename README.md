# GraphMining
Final Project of Graph Mining


# Packages required
```
pip install biopython
```


# Part1 : Python Parser for DBLP Citation Network

It is a python parser for [DBLP dataset](https://dblp.uni-trier.de/), the XML format dumped file can be downloaded [here](http://dblp.org/xml/) from [DBLP Homepage](https://dblp.org/).

This parser requires `dtd` file, so make sure you have both `dblp-XXX.xml` (dataset) and `dblp-XXX.dtd` files. Note that you also should guarantee that both `xml` and `dtd` files are in the same directory, and the name of `dtd` file shoud same as the name given in the `<!DOCTYPE>` tag of the `xml` file. Such information can be easily accessed through `head dblp-XXX.xml` command. As shown below
```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<!DOCTYPE dblp SYSTEM "dblp-2017-08-29.dtd">
<dblp>
<phdthesis mdate="2016-05-04" key="phd/dk/Heine2010">
<author>Carmen Heine</author>
<title>Modell zur Produktion von Online-Hilfen.</title>
...
```It is a python parser for [DBLP dataset](https://dblp.uni-trier.de/), the XML format dumped file can be downloaded [here](http://dblp.org/xml/) from [DBLP Homepage](https://dblp.org/).

This parser requires `dtd` file, so make sure you have both `dblp-XXX.xml` (dataset) and `dblp-XXX.dtd` files. Note that you also should guarantee that both `xml` and `dtd` files are in the same directory, and the name of `dtd` file shoud same as the name given in the `<!DOCTYPE>` tag of the `xml` file. Such information can be easily accessed through `head dblp-XXX.xml` command. As shown below
```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<!DOCTYPE dblp SYSTEM "dblp-2017-08-29.dtd">
<dblp>
<phdthesis mdate="2016-05-04" key="phd/dk/Heine2010">
<author>Carmen Heine</author>
<title>Modell zur Produktion von Online-Hilfen.</title>
...
```

# Preparing the dataset
A sample to use the parser:
```python
def main():
    dblp_path = 'dataset/dblp.xml'
    save_path = 'article.json'
    try:
        context_iter(dblp_path)
        log_msg("LOG: Successfully loaded \"{}\".".format(dblp_path))
    except IOError:
        log_msg("ERROR: Failed to load file \"{}\". Please check your XML and DTD files.".format(dblp_path))
        exit()
    parse_article(dblp_path, save_path, save_to_csv=False)  # default save as json format
```


# Part2 : Running for  Datasets

Please run the ```Yelp_dataset.ipynb``` for running the YELp dataset

Please run the centrality_measure.py for citation network analysis

All the rest of the analysis done using Microsoft Academic Dataset


# Conclusion Granger Casuality Measure

To run granger casuality measure please run the ```granger.ipynb``` file for that.
