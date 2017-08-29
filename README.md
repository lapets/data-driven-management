# Data-Driven Management
Course notes on data mechanics topics that underlie data-driven decision management and business analytics applications.

## The Opportunities and Challenges of Data

### Introduction

*Data* typically refers to a collection of structured, semi-structured, or unstructured information. We are concerned primarily with *digital* data, which includes anything from a text file, to a spreadsheet, to an enterprise database.

The term *metadata* typically refers to information *about* a data set or individual entries in that data set.

### Sources of Data in an Organization

Given a business question, what sources of data are available that can help answer it? What sources of data are necessary to answer it? While potential sources of data for business analytics can vary across scenarios, it is possible to build a [taxonomy of common sources](http://cambridgeservicealliance.eng.cam.ac.uk/resources/Downloads/Monthly%20Papers/2014_March_DataDrivenBusinessModels.pdf).

In particular, we are interested in data sets that relate directly or indirectly to some aspect of the organization. These can be broken down in one way as presented below:
* Internal data sources within the organization
  * Existing data sets already being generated and/or stored in digital form
    * Structured data
    * Semi-structured or unstructured data
  * Potential assets and business activities within the organization that can be surveyed, measured, and/or tracked to generate new data sets
    * Tracking information and measurements
      * Existing assets
      * Internal events
      * Interactions with other organizations
      * External opportunities
    * Exploratory or diagnostic experiments conducted within the organization
    * Crowd-sourced data
* External data sources available from other entities or organizations
  * Acquired or purchased data sets
    * Relevant data sets provided by commercial organizations
  * Data provided by customers
    * Social networking and social media
    * Direct communications from customers
  * Free and open data sources
    * Relevant data sets provided by government and non-profit organizations

> **Discussion:** Given a description of an organization, generate a list of possible data sets that can be identified or generated.

### From Assets and Activities to Data

Once the assets and activities from which we want to derive data have been identified, we need to identify the means and resources available to the organization to collect the desired data sets. It may be the case that additional resources are required to collect the desired data.

> **Case Study**

> **Multiple-Choice:** Answer questions about the case study.

### Surveys/Experiments as a Data Source

### Data Provenance and Data Quality

The *provenance* of a data set or stream (or an item therein) is a record of its origin and, possibly, its lifespan (including to whom it can be attributed, from what location it was obtained, from what other data sets it was derived, by what process this derivation was accomplished, and when all this occurred).

> **Multiple-Choice:** Answer questions about provenance and quality of data given small descriptions of scenarios.

### Data Storage, Longevity, and Security

When procuring or generating a data set or implementing a data stream, it is important to consider several logistical issues. The answers to the questions below can be driven by *how* and *by whom* the data will be used.

* With what frequency will a data set be generated, retrieved, or updated? What is the expected quantity of data per unit time? What is the cost to store this amount of data?
* Is the data's availability critical? How quickly might it be necessary to obtain a current or past instance of a data set?
* Is there sufficient storage to store all data, or will some data need to be discarded after a certain period of time?
  * A conservative approach might be to store as much data as the existing storage resources allow.
  * A lean approach might be to discard data immediately after it has been used. This may make it more difficult or impossible to determine the provenance of a result (unless provenance is tracked with sufficient granularity).
* Are there security risks associated with storing the data?
  * Should the data be encrypted at rest or during transmission?
  * Should security concerns influence the longevity of the data? Storing data for longer periods of times increases the timespan during which the data could be compromised.
  * Is the data subject to regulations such as HIPAA or FERPA? This can constrain how software that processes the data must be built, the hardware on which the data is stored, and even the security practices and personnel policies in effect at the facilities in which the hardware is maintained.

> **Multiple-Choice:** Identify appropriate resources necessary to maintain data sets (at different scales, different longevity/frequency requirements).

## Data Mechanics

### Introduction

In this part we formally introduce the building blocks that will allow us to discuss and reason about data sets and transformations on data sets. While different communities may use different sets of [terminology](https://en.wikipedia.org/wiki/Relational_database#Terminology) to refer to the concepts presented below, the concepts themselves are largely consistent across disciplines. A thorough understanding of the concepts themselves will allow you to navigate any scenario or tool (whether it is Microsoft Excel or a production SQL database) by first identifying the concepts at play and then establishing a mutually agreed-upon terminology with your colleagues or collaborators.

### Data Schemas and Data Sets

A *dimension* is some mathematical object. Examples of sets include the non-negative integers (i.e., `{0, 1, 2, 3, ...}`), the set of all strings (i.e., `{"a", "b", "c", "ab", "ac", "cb", ...}`) and so on.

A *record* is a mapping from a set of *attributes* (typically strings) to *values* drawn from some set. One example is `{"name": "Alice", "age": 25}`.

A *data set* is an unordered collection of records. A data set could be viewed/treated as a table within a data base (e.g., see [attribute-value system](https://en.wikipedia.org/wiki/Attribute-value_system)).

> **Exercise (Numerical Input):** Provide some basic information about the imported data set using basic tool features.

### Common Data Transformations

In general, any algorithms that operates on an input data set and produces an output data set is a data transformation. However, we can identify a variety of simple data transformations that occur frequently and can act as basic building blocks for more complex transformations. By referring to these buildling blocks we can (1) reuse common transformations and compose them to build larger ones, or (2) we can break down more complex transformations in order to reason about their properties (in terms of performance, provenance, security, and so on).

A *filter* or *selection* operation takes a data set as an input and produces an output that is a subset of that data set.

A *projection* operation takes a data set and applies some function to every record to produce an output data set. This output data set has *the same number of records* as the input data set, though the individual records themselves may have different attributes.

> **Exercise (Text Input):** Defining basic data transformations (filtering and projections) to accomplish an analytics task.

### Advanced Data Transformations

An *join* operation takes two data sets *A* and *B* and an attribute that appears in both data sets. It then looks through every possible pair of records (one record from *A* and one record from *B*) and keeps only those pairs in which the values for the attributes are the same.

An *aggregation* operation takes a data set, an index attribute, a target attribute, and an operation (such as counting, summation, maximum, and so on). It then separates all records into collections by index. For each collection, it combines the target attribute values in all the records within that collection using the operation (obtaining a single value). It then returns a new data set that maps each unique index attribute value to the corresponding aggregate of target attribute values.

> **Exercise (Numerical Input):** Using aggregations and joins to accomplish an analytics task.

### Data Cleaning and Normalization

#### Data Normalization

#### Joining Data Sets

When joining multiple data sets, two common issues may arise: differences in the schemas and differences in semantics.

> **Peer:** Integrate two or more data sets from different sources (different scales, some missing data).
