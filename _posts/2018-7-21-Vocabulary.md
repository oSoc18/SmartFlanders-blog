---
layout: post
title: Vocabulary for Smart Flanders
---
Publishing Linked Open Data isn't all about data. You also need to describe every piece of data for other users.
To describe your data you can use something called: `vocabulary`, but where do you get these?

## The World Wide Web

There are several parties on the World Wide Web which already publish some vocabulary on their website. 
You can reuse them in your own Linked Open Data. If you do that, others who already use the same vocabulary 
can easily read your data and more important: understand your data.

### Some examples:
- [https://schema.org](https://schema.org)
- [https://lov.linkeddata.es/dataset/lov](https://lov.linkeddata.es/dataset/lov)
- [https://data.vlaanderen.be/ns](https://data.vlaanderen.be/ns)

## Creating your own

If nothing is available that suits your application, you can always create the vocabulary yourself.
In case you have some experts at your disposal you can create immens detailed vocabulary but it's not always needed to publish some Linked Open Data. 

If you want to make your URIs persistent (you really should!), you can use [w3id.org](https://w3id.org) or create your own URIs. An example can be found in their [Github repository](https://github.com/perma-id/w3id.org/blob/master/BCI-ontology/.htaccess).

### Examples

#### Highly detailed
If you want highly detailed vocabulary you need a team of experts to manage and create the vocabulary. An example of this can be found [here](http://download.fortiss.org/public/bm/ontology/).

#### Sufficient for most of the time
You can limit yourself to RDFS and define some classes and properties like they did for [Linked Connections](https://linkedconnections.org). You can find an example of their vocabulary [here](https://github.com/linkedconnections/vocabulary/blob/master/vocabulary.ttl).

You won't get super detailed vocabulary with this approach, but it's doable for individuals and small organisations who are starting with Linked Open Data. 

## How did we get our vocabulary?

We found all our vocabulary online including the vocabulary from Toegankelijkheid Vlaanderen (ToeVla).
They had a research project a couple of years back where they used Linked Open Data in a mobile app, 
the app is abandoned, but the vocabulary still exists. We reused it since it mapped easily on the ToeVla data dump we received.

To create a persistent URI for this project we used w3id.org as well. If you go to [https://w3id.org/smartflanders](https://w3id.org/smartflanders), you will land directly on our blog.

### Overview

We used several vocabulary sources to publish the building data as Linked Open Data. 
Below, you can find a list of all the vocabulary sources we used:

- [https://schema.org](https://schema.org) for anything that wasn't available in the specialized vocabularies
- [https://data.vlaanderen.be/doc/applicatieprofiel/gebouw](https://data.vlaanderen.be/doc/applicatieprofiel/gebouw) to describe a building. Thanks to [OSLO](https://overheid.vlaanderen.be/producten-diensten/OSLO2) for sharing this application profile that helped us pick the right vocabularies!
- [https://data.vlaanderen.be/doc/applicatieprofiel/dienstencataloog](https://data.vlaanderen.be/doc/applicatieprofiel/dienstencataloog), [http://purl.org/vocab/cpsv](http://purl.org/vocab/cpsv) and [http://data.europa.eu/m8g/hasChannel](http://data.europa.eu/m8g/hasChannel) to describe a service. Thanks to [OSLO](https://overheid.vlaanderen.be/producten-diensten/OSLO2) for sharing this application profile that helped us pick the right vocabularies!
- [OSLO](https://data.vlaanderen.be/ns#Vocabularia) used in combination with the application profiles from OSLO
- [https://www.w3.org/2003/01/geo/wgs84_pos](https://www.w3.org/2003/01/geo/wgs84_pos) for GPS position information.
- [https://www.w3.org/ns/dcat#](https://www.w3.org/ns/dcat#) and [http://xmlns.com/foaf/0.1/](http://xmlns.com/foaf/0.1/) to create a structured catalogue
- [http://semweb.mmlab.be/ns/wa#](http://semweb.mmlab.be/ns/wa#) for the ToeVla data
