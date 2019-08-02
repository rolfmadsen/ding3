# ding3

The purpose of this repository is, for the time being, to experiment with different methods to write a specification for the next generation of DDB CMS.

## Global navigation

## Front page

## Sections

## News

## Events

## Library brances

### Opening hours

## Search

!(Screenshot of search result page)[]

### Prerequisites

- Profile.
- Agency.
- Client credentials for Opensearch API.
- Client credentials for FBS API.

### User story diagrams (PlantUML)

![Search field](http://www.plantuml.com/plantuml/proxy?cache=no&fmt=svg&idx=0&src=https://raw.githubusercontent.com/danskernesdigitalebibliotek/ding3/master/PlantUML_user-story-diagrams/Search/search.puml)

![Search result](http://www.plantuml.com/plantuml/proxy?cache=no&fmt=svg&idx=1&src=https://raw.githubusercontent.com/danskernesdigitalebibliotek/ding3/master/PlantUML_user-story-diagrams/Search/search.puml)

### User story functional specification

| Story ID 	| As a... 	| I can ...                                                      	| So that ...                                                               	|
|----------	|---------	|----------------------------------------------------------------	|---------------------------------------------------------------------------	|
| S001     	| Patron  	| Perform a search query                                         	| I can see the search result.                                              	|
|          	|         	|                                                                	|                                                                           	|
| Flow     	| Step    	| When ...  [Syntax: actor|action|element]                          | Then ... [Syntax: element|reaction]                                           |
| Main     	| 1       	| the patron clicks in the search field                          	| the searchfield becomes active                                            	|
|          	| 2       	| the patron inputs text in the seach field                      	| the autocomplete function displays suggestions from the Ortograf service. 	|
|          	| 3a      	| the patron clicks on the search profile dropdown menu.         	| the search profile drop down menu opens                                   	|
|          	| 3a1     	| the patron selects a value in the search profile dropdown menu 	| the search profile dropdown menu displays the selected value              	|

### Search field and autocomplete

![Search result](http://www.plantuml.com/plantuml/proxy?cache=no&fmt=svg&idx=0&src=https://raw.githubusercontent.com/danskernesdigitalebibliotek/ding3/master/PlantUML_sequence-diagrams/search/search-field-and-autocomplete.puml)

### Search field - Search profile

### Facet browser

### Sort

### Search result

#### Information

#### Work collections

Scenario display a work in the search result

#### Bibliotek.dk alternative search

#### Universal alternative Search

#### Pagination

## Loan status

## User profile

## References

PlantUML Sequence diagram - http://plantuml.com/sequence-diagram
Gherkin syntax - https://cucumber.io/docs/gherkin/reference/
Table to markdown generato - https://www.tablesgenerator.com/markdown_tables#
User story functional specification - http://www.its-all-design.com/an-agile-functional-specification/
PlantUML reference guide - http://plantuml.com/guide