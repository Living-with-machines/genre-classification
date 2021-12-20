# Genre Classification

What we mean by 'genre' is complex, open to question, and subject to temporal change. This work will largely ignore such complexity; this is one reason why we refer to the task as 'crude' genre detection.

However, by way of background context, in this section we provide a brief overview of genre classification and how it has been approached/understood within GLAM and Digital Humanities research.

## Machine Learning and Genre Classification from a GLAM Perspective

The collections of many GLAM institutions are growing rapidly owing to digitisation of physical collections and ingest of new ‘born digital’ materials. This is happening at a time of significant development of machine learning across a number of domains. Machine learning models are increasingly able to perform well on a range of tasks, including working with images (computer vision), tabular data, and written text (natural language processing). As a result, there is a growing interest in the possibility of using machine learning to create, or help create, metadata for these collections.

The desire to use computational methods to work with textual data is not new, and there are many pre-existing non-machine learning-based approaches that can be useful for working with collection items. For instance, one common approach to information retrieval uses term frequency–inverse document frequency [tf-idf](https://en.wikipedia.org/wiki/Tf%E2%80%93idf) to determine which words within a document are particularly important: the words ‘and’ or ‘not’ are far less likely to be useful for finding information about medieval religious practice than the word ‘monastery’, for example.

### Brief Reminder: Machine Learning

For most of this tutorial we assume you have some familiarity with machine learning, but the following gives a short overview of machine learning as a reminder.

Whilst approaches like [tf-idf](https://en.wikipedia.org/wiki/Tf%E2%80%93idf) work well for many tasks, there are some tasks for which machine learning may be more appropriate. A common example of such a task might be spam detection; this involves labelling a set of text strings as being ‘spam’ or ‘not spam’. There are various ways in which we could try and tackle this. As a starting point we could try writing some rules to help us decide if a message contains spam:

```python
spam_words = "Blockchain", "Bitcoin", ...

if spam_word appears in email:
    email_type = spam
else:
    email_type = not_spam
```

We can immediately see some of the challenge and limitations of this kind of approach. For a start, some people may not share the same withering opinion of “Blockchain” and “Bitcoin” and may want to receive emails on these topics - in this case the words we have chosen for spam are incorrect.

We will also need to maintain this list of spam words, which could get very time consuming. We might also need to rely on more complex rules to refine this crude approach by setting some kind of threshold for the number of times a spam word appears within the text, or by looking at combinations of words - but again this can quickly become quite complicated.

One other major limitation with this approach (which is something we need to consider with machine learning too) is that the world changes all the time. The types of words that appear in spam emails will change. The people who create these spam emails will likely change their approach to try and get around your spam filter. The machine learning approach, on the other hand, uses examples of 'spam' and 'not spam' to ‘learn’ how to predict these labels for new unseen examples. We train some type of machine learning model on a set of training data - in this case, the training data will be a set of emails containing examples of 'spam' and 'not spam'. The model will then 'learn' from this data which patterns indicate spam. These patterns may end up being quite complex, but, because we are using a machine learning approach we don't need to worry about what these patterns actually look like; if everything goes to plan the machine learning model will learn these patterns for itself.

## How is Machine Learning Being Used in Relation to Metadata?

There are a wide range of ways in which machine learning can be utilised as part of metadata processes. We won’t cover all of these in this chapter but will highlight some key tasks and briefly mention how the same machine learning task can be used in very different ways.

### Automated Subject Indexing

> “Choose a controlled subject vocabulary and train Annif on already indexed documents – it can then suggest subjects for new documents!” - https://annif.org/

Annif {cite:ps}`osma_suominen_2021_5654173` is a tool which aims to provide automated subject indexing for documents. The website includes a demo showing the results from different models. As an example we can see the subjects suggested when we put in a relatively short document - Theses On Feuerbach {cite:ps}`marx_2021`. The 15 suggested terms generated from the “YSO NN Ensemble English” model:

- philosophy
- religiousness
- religion and religions
- mysticism
- philosophy of religion
- theories of truth
- secularisation
- society
- secularism
- religious processions

Based on the input text many of these seem reasonable, but of course how useful they are depends on where and how these subject terms will be used. For example, if we were using the subject term ‘philosophy’ in a broad digital collection it would be very useful to have this subject term.  If however, we’re building a corpus of digitised texts on the topic of philosophy then this subject term is not particularly helpful. This points to the importance of making sure we understand what our goal is when using a model, as this will shape what is useful or not.

### Machine Learning Supported Metadata Evaluation

Another approach where machine learning has been used is to evaluate the quality of existing metadata records. “Automatically evaluating the quality of textual descriptions in cultural heritage records” is an example of this kind of approach {cite:ps}`lorenzini_rospocher_tonelli_2021`

In this paper the authors intended to classify the quality of metadata by treating it as a 'binary classification' task i.e. labelling the data as either high quality or not. The authors of this paper achieved an [F1 Score](https://en.wikipedia.org/wiki/F-score) of `0.85` with their approach.

### Machine Learning to Fill Metadata Gaps

Another example of using a computational model to create metadata where it doesn’t, or only partially, exists. An example of this is “Automated Language Identification of Bibliographic Resources” {cite:ps}`morris2020`

This work sought to address a problem of missing language codes in British Library Catalogue records: “An analysis of the British Library catalog in October 2018 revealed that this language code was not populated in nearly 4.7 million records.”{cite:ps}`morris2020`
Machine learning was applied to automate the identification of languages in the catalogue.
This work demonstrates an example of using machine learning to address a relatively narrow but important task - language identification - which needed to be done at a scale in which manual intervention would be difficult.

### Crude Genre Classification?

We will outline our approach briefly in the next chapter.
