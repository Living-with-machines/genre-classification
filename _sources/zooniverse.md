# Overview of the Project: Classifying British Library Books By Genre

Starting in 2005, the British Library (BL) worked in partnership with Microsoft to digitise a selection of out-of-copyright 18th and 19th century texts. This collection was subsequently made openly available in a number of formats, across a number of platforms. Throughout this document, the collection will be referred to as "{term}`Microsoft Digitised Books`".

The collection covers ~49,455 titles (~65,227 volumes) published between 1789 and 1914.

The metadata for these books is of variable quality and is not comprehensive. [British Library Labs](https://www.bl.uk/projects/british-library-labs) would like to be able to release subsets of the collection – all poetry, or all publications from a particular country, for example – as datasets for research. However, lack of good quality metadata means that this is not yet possible.

## Crowdsourcing Metadata from British Library staff

In order to revise and enrich existing metadata, a {term}`crowdsourcing` project was setup on the [Zooniverse](https://www.zooniverse.org/) platform by Victoria Morris (a member of the BL's [Metadata Standards](https://www.bl.uk/collection-metadata/strategy-and-standards)). The aim of this project was to enhance records for Microsoft Digitised Books by providing information about:

  - Country and place of publication
  - Date of publication
  - Edition
  - Language(s) of content
  - Literary form (fiction or non-fiction)
  - Genre (for fiction items)
  - Subject

The scope of the term "literary form" was specific to this project: "fiction" was interpreted broadly as "creative writing", thus would include poetry and drama. This might not be the same definition of "fiction" as would be appropriate in other context, particularly if identifying narrower or 'micro' genres.

### Zooniverse Task Setup

Title pages for Microsoft Digitised Books were loaded to an interface built using the Zooniverse platform. The interface allowed users to view the title page, and to record bibliographic metadata for the fields specified above. For practical expediency, books were separated into the following batches:

- Books written in the English language
- Books written in French and German
- Books written in other languages
- Books for which the language of content is not known

We will return to this language breakdown in later sections of the book.

When a user accessed the Zooniverse project, they were able to select the language of the books that they would like to annotate. Once a language had been selected, they were presented with the title page of a book, and  were asked to provide the following metadata elements for that book:

  - Language; language of summaries/abstracts; language of original (for translations)
  - Publisher
  - Place and country of publication
  - Date of publication
  - Edition
  - Form/genre (choice of FAST headings)
  - Subject (choice FAST headings)

These metadata elements were chosen because: (a) they were often missing from the records, and (b) it should be possible for participant to either transcribe or infer the relevant information from the title page. Participants were also provided with a link to the full text in case they felt it necessary to refer to the complete resource.

The annotations were exported from the Zooniverse platform. Some processing was done to make this exported format easier to work with. We don't provide the 'raw' Zooniverse export data since it contains personal data but you can find the notebook for processing the zooniverse data here #TODO add link once repository moved.

## Living with Machines

The Living with Machines project has been working with the Microsoft Digitised Books. In order to facilitate computational analysis of this collection ‘at scale’, it was felt it would be useful to be able to facet the collection by genre.

Whilst a detailed breakdown by genre (see for example the [MARC Genre Term List](https://www.loc.gov/standards/valuelist/marcgt.html)) might be desirable, even a high-level binary classification of texts as  being either *fiction* or *non-fiction* would allow for a more nuanced ability to work with books at scale, especially since we might expect both the content and language of these two broad genres to be quite different.

Although the Zooniverse crowdsourcing data was not originally collected with this task in mind, it did include genre classifications which we believed could be useful for developing a machine learning model to break down the full collection into genre-based subsets. The majority of this Jupyter Book outlines the steps taken in more detail. If you want to skip ahead to this you can jump to the next chapter. Alternatively, the next section gives a bit of background to this interest in genre from the perspectives of GLAM and History/Digital Humanities.
