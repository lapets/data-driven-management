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



### Data Schemas and Data Sets



### Common Data Transformations



### Advanced Data Transformations



### Data Cleaning and Normalization


