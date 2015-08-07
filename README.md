YeastMine
=========

* Scripts using [YeastMine](http://yeastmine.yeastgenome.org/yeastmine/begin.do) (populated by [SGD](www.yeastgenome.org/) and powered by [InterMine](http://intermine.github.io/intermine.org/)) to collect [Saccharomyces Genome Database](www.yeastgenome.org/) data.

* Running these scripts does require InterMine Python Web Service Client module be installed on the system. See nothes on installing the InterMine Python Web Service Client Module.

* These scripts will work on free [PythonAnywhere](https://www.pythonanywhere.com/) accounts because InterMine and YeastMine were graciously added to the [Whitelisted sites for free users](https://www.pythonanywhere.com/whitelist/) when I requested. THANKS, PythonAnywhere! See nothes on installing the InterMine Python Web Service Client Module on PythonAnywhere below.

* Of course, they will also work on your computer, server, or cloud instance or wherever you run Python programs that can access the internet. (On [SourceLair](https://www.sourcelair.com) `easy_install intermine  ` didn't work for adding the InterMine module, `pip install intermine` did work to install the InterMine module though.)





Installation of InterMine Python Web Service Client Module
----------------------------------------------------------

As described at [here](http://yeastmine.yeastgenome.org/yeastmine/api.do?subtab=python) you intstall the module on your system by

    $ easy_install intermine

(Dollar sign is used to indicate prompt. Don’t include that in your command.)  
You may need to do that as a superuser, i.e. include `sudo` at the start of that command, depending on how your system is set up.


If you are choosing to use a [PythonAnywhere](https://www.pythonanywhere.com/) account, you still need to install the InterMine Python Web Service Client Module to your individual account. It is done very similarly. You just need to additionally pass the user flag ‘--user ', as described [here](https://www.pythonanywhere.com/wiki/InstallingNewModules).
 
    $ easy_install --user intermine


On [SourceLair](https://www.sourcelair.com) that while `easy_install intermine  ` didn't work, `pip install intermine` did work to install the InterMine module.


Running the scripts
------------------
Add the script to your current directory and issue a command to tell python to run it.
Typically,

    python scriptname.py


For example,

    python protein_sizes_sorted.py

You'll probably want to direct the output to a file.

    python scriptname.py > output_filename.txt


Find more information on general installing and running InterMine [here](http://yeastmine.yeastgenome.org/yeastmine/api.do?subtab=python). 

Descriptions of the Scripts
---------------------------

- counting_amino_acid_residues_in_all_yeast_proteins.py

>Uses YeastMine to fetch information on all verfied proteins (currently 5917 mid-2105) and produces a file containing a sorted table of the counts and percent of occurences of amino acid residues in all the yeast proteins. The table is sorted in decreasing order with the most abundant amino acids at the top. The table can easily be pasted into or opened in Excel or Google Spreadsheets as it is tab-separated value document. The way the code is arranged you can easily substitute the part that accesses YeastMine to specify your own subset list of proteins to analyze for amino acid content.

- residue_clustering_determinator_ALL_proteins

> Uses YeastMine to fetch information on all verfied proteins (currently 5917 mid-2105) and produces a file containing a sorted table of the density and clustering of certain amino acids.  The tables are sorted in decreasing order with the best scores for density/clustering at the top. The tables produced can easily be pasted into or opened in Excel or Google Spreadsheets as it is tab-separated value document. The way the code is arranged you can easily substitute the part that accesses YeastMine to specify your own subset list of proteins to analyze for amino acid clustering.

- finding_genes_in_list_with_SGD_Systematic_Name.py

> Takes a list of genes provided in the long SGD systematic name form and collects more user friendly version of name and information for each gene from YeastMine. It is suggested on the command line you redirect the output to a file yourself. Or adapt it to meet your needs.

- all_genes_and_flanking_sequences.py

> Uses YeastMine to fetch genomic regions (gene + 1kb upstream and downstream) for all yeast genes. This script doesn't produce a named file. It is suggested on the command line you direct the output to a file yourself. For example when running, `python all_genes_and_flanking_sequences.py > all_genomic_regions.txt'. Or adapt it to meet your needs.


- gene_with_flanking_sequences.py

> Uses YeastMine to fetch genomic region (gene + 1kb upstream and downstream) for a yeast genes. This script doesn't produce a named file. It is suggested on the command line you direct the output to a file yourself. For example when running, `python gene_with_flanking_sequences.py > POP1_genomic_region.txt'. Or adapt it to meet your needs. The example is written to use POP1 but you can edit it to your gene.

- protein_sizes_sorted.py

> Uses YeastMine to sort yeast proteins based on size. This script doesn't produce a named file. It is suggested on the command line you redirect the output to a file yourself. (There was an issue with this ---> see last comment in script.) Or adapt it to meet your needs.

Additional Info
----------------

Find out more about YeastMine and InterMine [here](http://yeastmine.yeastgenome.org/yeastmine/begin.do) and [here](http://intermine.github.io/intermine.org/), respectively.

You can also make your own custom [YeastMine](http://yeastmine.yeastgenome.org/yeastmine/begin.do) queries at the [site](http://yeastmine.yeastgenome.org/yeastmine/begin.do) by starting with the numerous provided `Templates`. You can even run them right there. Start with the templates by accesing `Templates` from the navigation bar torwards the top of InterMine's portal and then you can edit the templates them by choosing `Edit Query` button to access the Query builder interface. Now you have an option to run the query right there at the YeastMine site by pressing `Show results`.  
Or if you want the Python code to run that query integrated into your workflow or to further adapt, you then access the code by clicking on the `Python` link down at the bottom middle once you have your built Query. You can edit them further after using Python coding as well.
