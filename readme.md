
# SKOS Taxonomy for Echoes domains & activities

<img width="1881" height="545" alt="Skos resume" src="https://github.com/user-attachments/assets/90a70c00-1513-4fb3-8073-24fdeb1608f1" />

## Introduction
At the begining of echoes project, WP4 has selected some domains and activities to explain the project to partners.
This data was retrieved and used for cartography purposes.
Once this cartography was complete, we thought that other applications would need this taxonomy.

We therefore created this project to semantically annotate and standardize this taxonomy with the aim of making it reusable, as suggested by the FAIR principles.

In order to explain the technical concept from start to finish, we have described our use case.

Next, if the Echoes project (WP4) approved, we will explain how to maintain such a semantic taxonomy, so that if the Echoes project creates a new version, all applications than use this taxonomy can update the change.

## Standardization
In the world of the semantic web, the W3C has created a standard called [SKOS (Simple Knowledge Organization System)](https://en.wikipedia.org/wiki/Simple_Knowledge_Organization_System), which can be used to represent classification.

The taxonomy used in ECHOES is a tree. So, concepts can be organized in hierarchies using broader-narrower relationships.

For example : 
The domain "Creation, Mediation, Dissemination", contain narrower concepts like :
* Teaching
* Publication
* Exhibition
* Artistic creation

SKOS organizes this data in a specific format in order to preserve the semantic relationships between them within the data.

This standard is well known around the world, so we believe it is the best way to publish this taxonomy so that other applications can also use it.

SKOS can be serialized in many syntaxes, such as Turtle (TTL), JSON-LD, or XML.

We will see that it is important to publish the taxonomy in several syntaxes if we want it to be used as widely as possible.

For the Echoes project, it is a common controlled vocabulary that can be shared with anyone who wants to display, filter, or classify data using this taxonomy.

## Technical explanation

<img width="2634" height="1378" alt="Using SKOS png" src="https://github.com/user-attachments/assets/084d3e7b-fe99-45a3-a791-3fb472b8786e" />

### Step 1 - Creation of turtle (TTL) file

We manualy create the turtle file using [SKOS specification](https://www.w3.org/TR/skos-reference/).

### Step 2 - Conversion to JSON-LD

Our ETL (Extract, Transform, Load) Software work with JSON. So, we convert turtle to JSON-LD.

### Step 3 - Conversion to JSON-LD Framed

In JSON-LD has a serialisation that is more readable. So we add a "JSON-LD Framed" in the directory.
We dont't use this serialisation in our project, but other application can use it.

### Step 4 - Transformation to JSON

Our cartography software waits for input, specific JSON, so we use an ETL to transform the JSON-LD in simple JSON.

### Step 5 - SemApps Importers

[Our mapping software](https://semapps.org) uses an [import module](https://semapps.org/docs/middleware/importer/) before saving data in its triplestore in RDF format.

### Step 6 - Display taxonomy

The last step display the taxonomy in our user interface, so that user can filter ECHOES organizations using the taxonomy.

Here we come :)

# Conclusion

Our use case is one among many others. 
It is important to understand that this standardization allows the ECHOES project to create a common controlled vocabulary that can be reused by all potential applications in the heritage sector.
