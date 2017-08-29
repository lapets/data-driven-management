# Data-Driven Management
Course notes on data mechanics topics that underlie data-driven decision management and business analytics applications.

## The Opportunities and Challenges of Data

### Introduction

*Data* typically refers to a collection of structured or unstructured information. We are concerned primarily with *digital* data, which includes anything from a text file, to a spreadsheet, to an enterprise database.

The term *metadata* typically refers to information *about* a data set or individual entries in that data set.

### Sources of Data for an Organization


### From Assets and Activities to Data

It is important to consider the frequency with which a data set is generated, retrieved, or updated.

### Data Provenance and Data Quality

The *provenance* of a data set or stream (or an item therein) is a record of its origin and, possibly, its lifespan (including to whom it can be attributed, from what location it was obtained, from what other data sets it was derived, by what process this derivation was accomplished, and when all this occurred).

### Data Storage, Longevity, and Security

When procuring or generating a data set or implementing a data stream, it is important to consider several logistical issues. The answers to the questions below can be driven by *how* and *by whom* the data will be used.

* What is the expected quantity of data per unit time? What is the cost to store this amount of data?
* Is the data's availability critical? How quickly might it be necessary to obtain a current or past instance of a data set?
* Is there sufficient storage to store all data, or will some data need to be discarded after a certain period of time?
  * A conservative approach might be to store as much data as the existing storage resources allow.
  * A lean approach might be to discard data immediately after it has been used. This may make it more difficult or impossible to determine the provenance of a result (unless provenance is tracked with sufficient granularity).
* Are there security risks associated with storing the data?
  * Should the data be encrypted at rest or during transmission?
  * Should security concerns influence the longevity of the data? Storing data for longer periods of times increases the timespan during which the data could be compromised.
  * Is the data subject to regulations such as HIPAA or FERPA? This can constrain how software that processes the data must be built, the hardware on which the data is stored, and even the security practices and personnel policies in effect at the facilities in which the hardware is maintained.

## Data Mechanics

### Introduction

In this part we formally introduce the building blocks that will allow us to discuss and reason about data sets and transformations on data sets. While different communities may use different sets of terminology to refer to the concepts presented below, the concepts themselves are largely consistent across disciplines. A thorough understanding of the concepts themselves will allow you to navigate any scenario or tool (whether it is Microsoft Excel or a production SQL database) by first identifying the concepts at play and then establishing a mutually agreed-upon terminology with your colleagues or collaborators.

### Data Schemas and Data Sets

A *dimension* is some mathematical object. Examples of sets include the non-negative integers (i.e., `{0, 1, 2, 3, ...}`), the set of all strings (i.e., `{"a", "b", "c", "ab", "ac", "cb", ...}`) and so on.

A *record* is a mapping from a set of *attributes* (typically strings) to *values* drawn from some set. One example is `{"name": "Alice", "age": 25}`.

A *data set* is an unordered collection of records. A data set could be viewed/treated as a table within a data base (e.g., see [attribute-value system](https://en.wikipedia.org/wiki/Attribute-value_system)).

### Common Data Transformations

In general, any algorithms that operates on an input data set and produces an output data set is a data transformation. However, we can identify a variety of simple data transformations that occur frequently and can act as basic building blocks for more complex transformations. By referring to these buildling blocks we can (1) reuse common transformations and compose them to build larger ones, or (2) we can break down more complex transformations in order to reason about their properties (in terms of performance, provenance, security, and so on).

A *filter* or *selection* operation takes a data set as an input and produces an output that is a subset of that data set.

A *projection* operation takes a data set and applies some function to every record to produce an output data set. This output data set has *the same number of records* as the input data set, though the individual records themselves may have different attributes.

### Advanced Data Transformations

An *join* operation takes two data sets *A* and *B* and an attribute that appears in both data sets. It then looks through every possible pair of records (one record from *A* and one record from *B*) and keeps only those pairs in which the values for the attributes are the same.

An *aggregation* operation takes a data set, an index attribute, a target attribute, and an operation (such as counting, summation, maximum, and so on). It then separates all records into collections by index. For each collection, it combines the target attribute values in all the records within that collection using the operation (obtaining a single value). It then returns a new data set that maps each unique index attribute value to the corresponding aggregate of target attribute values.

### Data Cleaning and Normalization


