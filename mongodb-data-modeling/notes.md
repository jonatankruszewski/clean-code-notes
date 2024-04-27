# MongoDB Data modeling


## Lesson 1: Introduction to data modeling

## 01, Data modeling

- Data modeling is how data is stored and the relationship that exists among different entities in your data.
- Schema: organization of data in a database.
- Data accessed together should be stored together.
- Schema: What does my app do, how does my application do, what data Will I store, how users access this data.
- Benefits of a good data model:- Easier- queries more efficient- Use less resources (cpu, ram) - Cheaper

Polymorphism !== schemaless.
MongoDB has flexible schema model. Not schemaless.
You can have embedded documents.
You can normalize data by using references.

You can Embed or Reference data in MongoDB.
First understand usage, then model relationships.

Which of the following statements is/are true about data modeling? (Select all that apply.)
- [X] Data modeling is the process of defining how data is stored.  
- [X] Data modeling is the process of defining the relationships that exist among different entities in your data.
- [ ] Data modeling is the process of collecting data.

Which of the following are benefits of a proper data model? (Select all that apply.)
- [X] A proper data model makes it easier to manage your data.
- [X] A proper data model makes queries more efficient.
- [X] A proper data model uses less memory and CPU.
- [X] A proper data model reduces costs

Which of the following is a benefit of the document model?
- [X] The document model does not enforce any document structure by default. This means that documents even in the same collection can have different structures.
- [ ] The document model makes having a schema useless.
- [ ] The document model supports only simple relationships among data to make data wrangling easier.s


## Lesson 02: Types of data relationships

Different types of relationships
One to one: one property in one document
One to many: an array in one document
Many to many: ? no examples.

Embedding and referencing

Data accessed together should be stored together.
Looking through multiple collections has a performance cost and economic cost.

A. One-to-one relationshipYour Answer: Correct
Correct!

A one-to-one relationship is one of the most common types of relationships found in a database. One-to-one is a relationship where a data entity in one set is connected to exactly one data entity in another set.

B. One-to-many relationshipYour Answer: Correct
Correct!

A one-to-many relationship is one of the most common types of relationships found in a database. One-to-many is a relationship where a data entity in one set is connected to any number of data entities in another set.

C. Many-to-many relationshipYour Answer: Correct
Correct!

A many-to-many relationship is one of the most common types of relationships found in a database. Many-to-many is a relationship where any number of data entities in one set are connected to any number of data entities in another set.

D. One-to-zillions relationship

## Lesson 03

## Lesson 04
Embedding
one to one (can be done)
one to many (most used case)
or many to many (may introduce data duplication)

embedding avoids application joins
provide better performance for read
allows to update related data in a single operation

problems:
- overtime can become large, adding latency for reads. Slow performance for reads for users
- Unbounded documents may excheed the bson document treshold of 16 mb

## Lesson 05
references
save the id in another documents
sometimes called linking or data normalization

avoid duplication
smaller documents
but, need to join data

# Lesson 06

problems with data models

- avoid unbounded documents. 
- Hard pagination, take more space in memory, mau impact write performance.
- Storaga limit.
- Benefit: retrieve everything in one single read. In the case of "post comments" better to use multiple collections.

# Lesson 07

Schema anti patterns: massive arrays, massive numbers of collections, bloated documents, unnecessary indexes, queries without indexes, data accessed together but stored in different collections.

Tools to help: 
Data explorer: free with free tier atlas. Shows schema anti patterns. View storage size, total document,s etc. Indexes tabs shows stats of the indexes.
performance advisors: m10 tier and higher. can tell which indexes are redundant. 

Schema design patters are guidelines that help developer plan, organize and model data.



Data modeling for mongodb overview

3 design phases
Workload identification
- main entities
- which entities changes over time, and how
relationships identification
Patterns application

golden rule: accessed together should be stored together


Identifying DB workload

- Identify, quantify.
- Entities have attributes. 

Identify entities, quantify reads and writes.

When analyzing, do it from the user and application perspective (analytics queries)


