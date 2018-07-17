---
layout: post
title: Missing URIs
---

## ID'ing is a problem

A lot of data sets that are available today are just CSV, Excel, ... files or are available through an [API]().
Each data set uses its own unique identifier for every piece of data, for example an integer to indicate the row number in your Excel file.
Within that specific data set the identifier will be unique however, if you combine several data sets the identifier can be reused by several data sets.

This is a big problem! It's impossible now to identify a piece of data in a unique way. For example, if two people have the same social security number
how can you be sure that you are sending the right taxes envelope to the right person?

## URIs are the solution

### What are URIs?

URI (Uniform Resource Identificator) is way to indicate the location of a resource.
A resource can be anything:

- A person
- A door
- A plant
- An elevator
- ...

Basically, an URI identifies something you can touch in the real world. It has the same purpose as the social security number on your eID. The social security number identifies you as an individual in the real world. You read more about URIs [here](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier).

URIs  up in several parts. You can only generate unique URIs since only one person of organisation has access to each part of the URI.

`https://basisregisters.vlaanderen.be/api/v1/gebouwen/19624094`

If you look at this URI you can see that only the webmaster of `basisregisters.vlaanderen.be` can generate unique identifiers for `gebouwen`.
Every part of the URI has its own organisation that manages the domain. Only the people behind `.be` can create `vlaanderen.be` nobody else!

### Toegankelijkheid Vlaanderen (ToeVla)

ToeVla provided us with a dump of their database in an Excel sheet. We converted the Excel sheet to a CSV file to process it more easily.
You can find an excellent tutorial to convert Excel sheets to CSV files on the [Microsoft Office support website](https://support.office.com/en-us/article/Import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba).

The issue which arose after the CSV export was that ToeVla doesn't have a unique URI for each entry in their data set.
The building registry from `data.vlaanderen.be` has a unique URI for each building in Flanders.
We need to match the building data from the building registry with the ToeVla database entries.

To match these buildings we focused on the addresses of the buildings. Only those fields are matching between the ToeVla database and the building registry.
However, another problem showed up! One address can have multiple building units (offices, station, public toilets, ...) and one building can have multiple addresses to describe multiple entrances.

To circumvent this issue, we kindly ask the user to select the right building in the form we are building.
This isn't an ideal way to achieve our goal since the user can make a mistake and describe the 'wrong' building.
The best way to solve this issue would be convincing ToeVla to publish their data with the building registry unique URI for each building. This way we can match the URI and avoid mistakes from the user.
