---
layout: post
title: Problems with combining several data sets
---

## The problem

If you look today at all the data that's available on the Internet you will come across the following things:

- A lot of formats for every data set. When we say a lot, we really mean a lot!
- Several datasets will provide the same type of information without combining their forces.
- Everyone has its own vocabulary
-  ...

The point here is simple: no standards are available to structure your data set to achieve interaction with other data sets!

## How we tried to tackle this problem

We tackled this problem using Linked Open Data. It's a standard developed with a simple purpose: structure your data set and link it with other data sets.
The Linked Open Data philosophy allows us to publish our data in a format like JSON-LD and easily transform it to other kinds of Linked Open Data formats automatically.
This is only possible if we defined our vocabulary first of course! In order to unify the vocabulary, companies and communities created several websites where they publish their standardized vocabulary.

For example:

- [data.vlaanderen.be/OSLO](https://data.vlaanderen.be/ns)
- [schema.org](https://schema.org)
- [Linked Open Vocabulary (LOV)](http://lov.okfn.org/dataset/lov)

You can search for the vocabulary you're looking for on these websites and they will show you which vocabulary you may use for your data sets. They also mention when the vocabulary is applicable.

For example, the building address described by the [Flemish OSLO vocabulary](https://data.vlaanderen.be/ns/adres):
I summarized the text in English, the full description is available in the vocabulary in Dutch.

|       URI         | http://data.vlaanderen.be/ns/adres#Adres                                                  |
| Specialisation of | http://www.w3.org/2000/01/rdf-schema#Resource                                             |
|    Definition     | Information that allow us to define in a unique way to street, number, ... of a building. |
|      Usage        | Belgian address of a building								|

In the table above you can clearly see that the vocabulary is strictly defined. You know exactly when you have to use it, what's the definition of the vocabulary and so on.
This way we can fix the mixed vocabulary and easily combine several datasets! Each data set can extend each other and show any matches between them without writing complex code to map several data sets and check for duplicates in the data.
