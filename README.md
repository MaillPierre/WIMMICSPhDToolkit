# PhD Toolkit
This repository offers a list of tools and pieces of advice to new PhD students and other researchers.

## Bibliography

### Managing articles

* [Zotero](https://www.zotero.org/) is a good bibliography manager.
    * There is a Zotero plugin to use automatically SciHub to retrieve PDFs when they are not open access: https://github.com/ethanwillis/zotero-scihub.

* W3C recommendations can have a BibTeX bibliography entry using the site: https://w2.syronex.com/jmr/w3c-biblio.

### Looking for related works

#### Find PDFs

* [Google Scholar](https://scholar.google.com/) is the Google portal specialized for scientific articles. It will show the different versions of an article that are hosted on the web.

* [SciHub](https://sci-hub.se/): Bypassing paywalls is illegal, and you should NOT use a website such as [SciHub](https://sci-hub.se/) to enter a DOI and get the PDF you could not access in return.

* [HAL](https://hal.archives-ouvertes.fr/): All INRIA researchers have to upload their research articles in open access to [HAL](https://hal.archives-ouvertes.fr/).
    * You must upload the PDF of any article you publish while you are at INRIA. You can upload an author version as soon as it is accepted for publication.

* On Twitter (X) and on Mastodon, the hashtag [#canihazpdf](https://twitter.com/hashtag/canihazpdf) given with a reference to an article will signal to the community of researchers that you are searching for the PDF of this article.

#### Find articles

* [Connected Papers](https://www.connectedpapers.com/) gives you a view of the articles that are connected to a given paper in its field.

* [PURE Suggest](https://fabian-beck.github.io/pure-suggest/) gives you the list of the most related papers in relation to a list of given papers.

* [Litmaps](https://www.litmaps.com/) generates a visualization of the most relevant article related to a given paper.

## Writing

### Grammar, typos, and style

* [Hemingway editor](https://hemingwayapp.com/) gives you recommendations on the style of your English.

* [Grammarly](https://app.grammarly.com/) is a free grammar check in your browser. It works great with Hemingway.

* [Grammalecte](https://grammalecte.net/) is an open-source equivalent to Grammarly, for French.

* [outwrite](https://app.outwrite.com/) another Grammarly available in several languages

### LaTeX

* [The LaTeX article on Wikibooks](https://en.wikibooks.org/wiki/LaTeX) contains most of the commands that are useful for writing a LaTeX document.

* The `savetrees` package automatically reduces the size of the text of your article. There are 3 modes:

    * `\usepackage[subtle]{savetrees}`: Mostly reduce the insertion of whitespaces in text.
    * `\usepackage[moderate]{savetrees}`: Reduces spaces around figures, paragraphs, tables, etc., in a relatively non-style-breaking manner.
    * `\usepackage[extreme]{savetrees}`: Not recommended, it reduces everything it can reduce in the article.

* The `todonotes` package allows you to create notes in the PDF either in the margin or in the text itself. [An example of this is given in a dedicated file](latex_todonotes_example.md).

## Networking

* [ORCiD](https://orcid.org/) creates for you a unique identifier and a page in which you can concentrate your publications and links to your different pages on the web. It is very useful to share your publications with other services. It interfaces with HAL, Google Scholar, and many other services.

* [HAL](https://hal.archives-ouvertes.fr/) also generates an unique identifier for you, and it can generate a curriculum vitae for you from your publications.

* [ResearchGate](https://www.researchgate.net/) is one of the main social networks for researchers. It is particularly useful to find, or even request, PDFs directly on their author page.

* [Academia](https://www.academia.edu/) is another social network for researchers. It is particularly useful to find, or even request, PDFs directly on their author page.

## Conference/Journal finding

### Conference ranking

* [Conference ranks](http://www.conferenceranks.com/)

* [GII-GRIN-SCIE (GGS) Conference Rating](https://scie.lcc.uma.es:8443/)

## Datasets, Code and Experiments

### Code

* [Anonymous GitHub](https://anonymous.4open.science/) anonymizes your GitHub repo for double-blind submissions

### Datasets

* [Zenodo](https://zenodo.org/)

### [Using Virtual Environments in Jupyter Notebooks](./python_jupyter_envs.md)
