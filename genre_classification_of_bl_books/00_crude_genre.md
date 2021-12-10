# Crude Genre Classification

We saw in the previous chapter that there have been various approaches to metadata generation using machine learning methods. We also saw that one of the potential labels we had available to us to use was a 'genre' label which labelled a book `fiction` or `non-fiction`. We also had more granular labels from the FAST terms. However we decided to focus on initially trying to build a classifier which would put all books into one of these two categories.

This collapsing of all books into two genres will displease some but it offers some advantages:

- it keeps the task relatively simple, this allows us to focus on improving the data and model rather than having to define a more complex machine learning approach
- we have ready to use metrics for evaluating our approach
- we have 'crude' enough categories that we may be able to computationally generate some of our training data

Beyond these more pragmatic reasons we should also remember what our original aim was - to help us split a large corpus of books into different categories. Being able to select only fiction or non-fiction books from a collection is already massively helpful for many other tasks we might want to do with the collection.

## Our approach

Whilst we discus this more  as we move through the tutorial, it may be useful to have an overview of what we're trying to achieve and why:

- We have a set of digitised book which have some metadata attached, but often the field for genre is not populated.
- We also have a subset of this data that has annotations for genre produced via an internal crowdsourcing task.
- We want to train a machine learning model on this annotated data.
- We then want to apply this machine learning model to the whole collection of books so we have genre labels for all the books.

### What do we classify?

Whilst the above gives an overview of what we want to achieve we still have an open question of how we do it. The books we are working with have various metadata attached. Our training data has a bunch of this metadata along with a label for `fiction` or `non-fiction`.

We could potentially use all of this as input for our model to use when making it's prediction. This is something we tried as we were outlining our approach but we settled on using only the title of the book as input for the model.

#### Why not use the full text of the book?

We could potentially have used the full text of the book. However, we decided not to do this for a number of reasons. Firstly, the full text is often far too long to be used for most models we'd work with. We'd therefore have to decide which parts of the book to use. Some books will contain blank pages or illustration's with no text. We might theefore end up requiring fairly complex rules to work out which pages to use. Our model would also be a lot more computationally demanding. Whilst we may have some problems with classifying books from their title, the cost of doing this will be much less than user a large amount of book text.

Another reason we might want to use the title only is that we can more safely assume other people with a similar goal, of classifying the genre of a book, will also have this available to them. As a result the mode *might* be sligtly more reusable or adaptable. We'll get back to this in more detail in a [following chapter](05_sharing_our_model.md).

#### Why not use a knowledgebase?

Another reasonable objection to our approach is to ask why we need to use machine learning at all? There are other catalogues that might contain the information we need. Whilst this might be true for some titles, others may be unique to the collection we're working with. Another challenge of using a knowledgebase is that we will likely also have to do some work to resolve the possible matches for any titles we lookup. Whilst this isn't insurmountable it does mean that this approach won't necessarily be a huge amount more straightforward than our machine learning approach using the title of the book. A potential avenue for extending the approach we use here would be to combine a machine learning and knowledgebase approach to this problem but that is beyond what we'll cover in this tutorial (at least for the initial version).
