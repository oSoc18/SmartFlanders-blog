---
layout: post
title: Vocabulary for Smart Flanders
---
Publishing Linked Open Data isn't all about data. You also need to describe every piece of data for other users.
To describe your data you can use something called: `vocabulary`, but where do you get these?

## The World Wide Web

There are several parties on the World Wide Web which already publish a large catalogue of vocabulary. 
You can reuse them in your own Linked Open Data. If you do that, others who already use the same vocabulary 
can easily read your data and more important: understand your data.

### Some examples:
- [https://schema.org](https://schema.org)
- [https://lov.linkeddata.es/dataset/lov](https://lov.linkeddata.es/dataset/lov)
- [https://data.vlaanderen.be/ns](https://data.vlaanderen.be/ns)

## Creating your own

If nothing is available that suits your application, you can always create the vocabulary yourself.
This can be really hard and requires a lot of knowledge about the data you want to describe.

## How did we get our vocabulary?

We found all our vocabulary online including the vocabulary from Toegankelijkheid Vlaanderen (ToeVla).
They had a research project a couple of years back where they used Linked Open Data in a mobile app, 
the app is abandoned, but the vocabulary still exists. We reused it since it mapped easily on the ToeVla data dump we received.

### Overview

We used several vocabulary sources to publish the building data as Linked Open Data. 
Below, you can find a list of all the vocabulary sources we used:

- [https://schema.org](https://schema.org) for anything that wasn't available in the specialized vocabularies
- [https://data.vlaanderen.be/ns](https://data.vlaanderen.be/ns), [http://purl.org/vocab/cpsv](http://purl.org/vocab/cpsv) and [http://data.europa.eu/m8g/hasChannel](http://data.europa.eu/m8g/hasChannel) to describe the building data
- [https://www.w3.org/2003/01/geo/wgs84_pos](https://www.w3.org/2003/01/geo/wgs84_pos) for GPS position information.
- [https://www.w3.org/ns/dcat#](https://www.w3.org/ns/dcat#) and [http://xmlns.com/foaf/0.1/](http://xmlns.com/foaf/0.1/) to create a structured catalogue
- [http://semweb.mmlab.be/ns/wa#](http://semweb.mmlab.be/ns/wa#) for the ToeVla data
