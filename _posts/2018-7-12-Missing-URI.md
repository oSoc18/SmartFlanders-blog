---
layout: post
title: Missing URI's 
---

## ID'ing is a problem

A lot of datasets that are available today are just CSV, Excel, ... files or are available through an [API]().
Each dataset uses it's own unique identifier for every piece of data, for example an integer to indicate the row number in your Excel file.
Within that specific dataset the identifier will be unique however, if you combine several datasets the indentifier can be reused by several datasets.

This is a big problem! It's impossible now to identify a piece of data in an unique way. For example, if two people have the same social security number 
how can you be sure that you are sending the right taxes envelope to the right person?

## URI's are the solution

### What are URI's?

URI (Uniform Resource Locator) is way to indicate the location of a resource.
A resource can be anything:

- A person
- A door
- ...

URI's are splitted up in several parts. You can only generate unique URI's since only one person of organisation has access to each part of the URI.

`https://basisregisters.vlaanderen.be/api/v1/gebouwen/19624094`

If you look at this URI you can see that only the webmaster of `basisregisters.vlaanderen.be` can generate unique identifiers for `gebouwen`.
Every part of the URI has it's own organisation that manages the domain. Only the people behind `.be` can create `vlaanderen.be` nobody else!

### Toegankelijkheid Vlaanderen (ToeVla)

ToeVla provided us with a dump of their database in an Excel sheet. We converted the Excel sheet to a CSV file to process it more easily.
You can find an excellent tutorial to convert Excel sheets to CSV files on the [Microsoft Office support website](https://support.office.com/en-us/article/Import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba).

The issue which arised after the CSV export was that ToeVla doesn't have an unique URI for each entry in their dataset. 
The building registry from `data.vlaanderen.be` has a unique URI for each building in Flanders. 
We need to match the building data from the building registry with the ToeVla database entries.

To match these buildings we focussed on the addresses of the buildings. Only those fields are matching between the ToeVla database and the building registry.
However, another problem showed up! One address can have multiple building units (offices, station, public toilets, ...) and one building can have multiple addresses to describe multiple entrances.

To circumvent this issue, we kindly ask the user to select the right building in the form we are building. 
This isn't an ideal way to achieve our goal since the user can make a mistake and describe the 'wrong' building. 
The best way to solve this issue would be convincing ToeVla to publish their data with the building registry unique URI for each building, this way we can match the URI and avoid mistakes from the user.
