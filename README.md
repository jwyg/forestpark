## About

_Everything in the forest park_ is an extended invitation to partake in all activities available at a forest park in Scotland, according to search engine results. It explores how the web invites different kinds of relations with woodland areas, addressing page visitors as tourists and adventurers, hikers and holidayers, customers and conservationists.

It is composed from fragments of texts extracted from every Google Search result for [a forest park in Scotland](https://en.wikipedia.org/wiki/Queen_Elizabeth_Forest_Park). While search engines aim to order and optimise results according to their relevance for users and advertisers through crawling and algorithmic ordering, _Everything in the forest park_ collapses and reorders these indexed results to produce a speculative account of forest park life.

## Protocol

It was produced with the following protocol:

1.  Extract URLs from query results using [Sciences Po médialab Google Bookmarklet tool](https://medialab.sciencespo.fr/en/tools/google-bookmarklets/).
2.  Filter out non-HTML results (e.g. PDFs) and results relating to other places using [OpenRefine](https://openrefine.org/).
3.  Extract full text from filtered URLs using [Digital Methods Initiative Text Ripper tool](https://tools.digitalmethods.net/beta/textRipper/).
4.  Use [grep](https://en.wikipedia.org/wiki/Grep), [sed](https://en.wikipedia.org/wiki/Sed) and [sort](https://en.wikipedia.org/wiki/Sort_(Unix)) to obtain texts from query results addressing "you" and re-order alphabetically with the command:

```grep -i " you " results\_text.txt | sed 's/\[^a-z A-Z 0-9 ,.-:!\]//g' | sort -u > forestpark.txt```

5.  Remove menu items and references to particular place names.
6.  Generate audio with [say](https://ss64.com/osx/say.html):

```cat forestpark.txt | say -v Fiona -r 120 -o forestpark.aiff --progress```

7.  Create web page and final audio track using media and design elements from query results.
