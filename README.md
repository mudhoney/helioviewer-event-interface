# Helioviewer Event Interface
The Helioviewer Event Interface's mission is to provide a the tools and interface to make it as easy as possible to integrate new feature & event data sources into helioviewer.org.

This module managers performing the external HTTP requests and passing that data over to the relevant translator which converts the data into the appropriate format.
It also provides a standard framework to follow for translating one object into Helioviewer.
Finally, it manages querying these external data sources which makes this the place to perform optimizations for caching, making simultaneous requests, etc.

# Why?
Helioviewer's [Event Format](https://api.helioviewer.org/docs/v2/appendix/helioviewer_event_format.html) provides a standard object that helioviewer.org can parse and understand without any modifications to the application.
We would like to make it easy to finesse external data into this format for inclusion on Helioviewer.

## Requirements
1. The external data source must provide an HTTP API for accessing its data
2. The API must accept a start date and end date as input parameters
3. The API must return fields that specify a location on the sun

## Procedure
1. Add the API URL to the list of known data sources.
2. Create a definition that describes how to translate data into Helioviewer's format.