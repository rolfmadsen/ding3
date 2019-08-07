# ding3

The purpose of this repository is, for the time being, to experiment with different methods to write a specification for the next generation of DDB CMS.

## Global navigation

## Front page

- Promote content types to frontpage
    - Promote types to frontpage
        - Nyhed [boolean]
        - Begivenhed [boolean]

## Sections
Mangler afklaring: Skal Paragraphs modulet benyttes i stedet for Sectionsmodulet (Editorial base).

Indholdstyper:
- Tabroll
- Karusel
- Nyheder
- Arrangementer
- Sektioner

Panelser (https://upgrade-fbs.ddbcms.dk/admin/config/user-interface/ipe-filter)
- Campaign
- all_opening_hours
- Popular
- Interaction_pane
- ding_nodelist
- Serendipity_ting_object
- ding_tabroll-ding_frontpage_tabroll
- ding_event-ding_event_list_frontpage
- ding_event-ding_event_simple_list
- ding_groups-ding_group_overview_simple
- carousel
- ding_news-ding_news_frontpage_list

Ding nodelist (https://upgrade-fbs.ddbcms.dk/admin/config/ding/ding_nodelist)
- Liste over indholdstyper
- Standard mellemlagringstid (0s|15s|30s|1m|2m|3m|4m|5m|10m|15m|30m|1t|2t|4t|8t|12t|1d|2d|3d|4d|1u)
- Standard autoscroll forsinkelse for karusel [ms]

## News

- Number of news (https://upgrade-fbs.ddbcms.dk/admin/config/ding/news)

## Events

- Place2book indstillinger (https://upgrade-fbs.ddbcms.dk/admin/config/ding/place2book/defaults)
    - Default event maker radio:[list_of_branches]
    - Vedligehold kopi [boolean]
    - Kultunaut eksport [boolean]
    - Passivt arrangement [boolean]
    - Kapacitet [integer]
    - Ticket type [string]
- Place2book indstillinger - service (https://upgrade-fbs.ddbcms.dk/admin/config/ding/place2book)
    - Place2book service base URL [URL]
    - Place2book autorisation token [string]
    - Insert Place2book event makers path without leading slash [string]
    - Insert Place2book edit event path without leading slash [string]
    - Insert Place2book get event path without leading slash [string]
    - Insert Place2book update event path without leading slash [string]
    - Insert Place2book delete event path without leading slash [string]
    - Insert Place2book create event path without leading slash [string]
    - Insert Place2book create price path without leading slash [string]
    - Insert Place2book get prices path without leading slash [string]
    - Insert Place2book get price path without leading slash [string]
    - Insert Place2book update price  path without leading slash [string]
    - Insert Place2book delete price path without leading slash [string]
- Place2book indstillinger - mappings (https://upgrade-fbs.ddbcms.dk/admin/config/ding/place2book/mappings)
    - Event makers
        Event maker [Liste_af_branches]
    - Kultunaut age group
        - For alle [børn|unge|voksn|ældre]
        - For børn [børn|unge|voksn|ældre]
        - For studerende [børn|unge|voksn|ældre]
        - For unge [børn|unge|voksn|ældre]
        - For voksne [børn|unge|voksn|ældre]
        - For ældre [børn|unge|voksn|ældre]
    - Kultunaut export category
        - 

- Arrangementer på forsiden (<front>)
    - Antal arrangementer på forsiden
    - Vis kun arrangementer med markeringen "Vis på forsiden / "Promoted"
- Arrangementslisten (/events)
    - Antal arrangementer på arrangementslisten
    - Sortéring efter dato eller måned

- Generelt
    - Valuta

Kilde: https://upgrade-fbs.ddbcms.dk/admin/config/ding_event/settings

## Library brances

### Opening hours

## E-ressourcer / E-resurser (https://upgrade-fbs.ddbcms.dk/admin/config/ding/eresource)

- Overwrite the default e-resource category text

- https://upgrade-fbs.ddbcms.dk/node/add/ding-eresource
- https://upgrade-fbs.ddbcms.dk/admin/structure/types/manage/ding_eresource
- https://upgrade-fbs.ddbcms.dk/admin/structure/taxonomy/e_resource_availability
- https://upgrade-fbs.ddbcms.dk/admin/structure/taxonomy/e_resource_category

Mangler afklaring - Kan et overblik over e-ressourcer genereres bedre?

## Personalisering

- Ding serendipity (https://upgrade-fbs.ddbcms.dk/admin/config/ding/serendipity)
    - Aktivér caching [boolean]
    - Cache udløb [integer]
    - Grænse for hvornår serendipitetsopslag markeres som for langsomme [integer]
    - Serendipitets CQL fallback søgestrenge [string]
    - Serendipitet sidste fallback beskrivelse [string]

## Search

- Ding search service settings (https://upgrade-fbs.ddbcms.dk/admin/config/ding/provider/opensearch)
    - bliotekskode [integer]
    - Search service URL [URL]
    - Authentication
        - Use authentication [boolean]
        - Navn [string]
        - Adgangskode [string]
        - Gruppe [string]
    - Recommendation service URL [URL]
    - Search profile [string]
    - Infomedia web service URL [URL]
    - Akrivér logging [boolean]
    - Cache udløb [1m|5m|15m|30m|1t|3t|12t|1d|3d|1u]

- Search result boost (https://upgrade-fbs.ddbcms.dk/admin/config/opensearch/rank)

Omhandler rankering og boost af søgeresultatet.

- Search result ranking (https://upgrade-fbs.ddbcms.dk/admin/config/opensearch/ranking)
    - Enable custom ranking [boolean]
    - Custom ranking fields (0.*)
        - Type [phrase|word]
        - Feltnavn [kilde|titel|forfatter|emne|year_of_publish|material_type]
        - Vægt [1|2|3|4|5|6|7|8|9|10]
    default sort method (Best_matched)
        Type [best_match|general_rank|no_rank]
- Search result boost (https://upgrade-fbs.ddbcms.dk/admin/config/opensearch/boost)
    - Custom field boost values
        - Feltnavn [kilde|forfatter|emne|year_of_publish|material_type|sprog|isbn_number|klassemærke]
        - Værdi [string]
        - Vægt [integer]

!(Screenshot of search result page)[]

### Prerequisites

- Profile.
- Agency.
- Client credentials for Opensearch API.
- Client credentials for FBS API.

### User story diagrams (PlantUML)

#### Search field and autocomplete

- Opensearch search autocomplete settings (https://upgrade-fbs.ddbcms.dk/admin/config/opensearch/autocomplete)
-   Autocomplete service URL [URL]
-   Autocomplete settings
    - Max suggestions [integer]
    - Minimum string [integer]

![Search field](http://www.plantuml.com/plantuml/proxy?cache=no&fmt=svg&idx=0&src=https://raw.githubusercontent.com/danskernesdigitalebibliotek/ding3/master/PlantUML_user-story-diagrams/Search/search.puml)

#### Search result

![Search result](http://www.plantuml.com/plantuml/proxy?cache=no&fmt=svg&idx=1&src=https://raw.githubusercontent.com/danskernesdigitalebibliotek/ding3/master/PlantUML_user-story-diagrams/Search/search.puml)

### User story functional specification

| Story ID 	| As a... 	| I can ...                                                      	| So that ...                                                               	|
|----------	|---------	|----------------------------------------------------------------	|---------------------------------------------------------------------------	|
| S001     	| Patron  	| Perform a search query                                         	| I can see the search result.                                              	|
|----------	|----------	|----------------------------------------------------------------   |---------------------------------------------------------------------------	|
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

##### Periodicals

UX oplæg - https://projects.invisionapp.com/share/2XND9K1EVY6#/screens/319278647

[volumeYear]
Bind/vol. [volume], nr. [VolumeNumber]

Svarende til:

2018
Bind/vol. 2018, nr. 01

Behanldet i https://platform.dandigbib.org/issues/3146

#### Bibliotek.dk alternative search

#### Universal alternative Search

#### Pagination


## Lånerstatus

- FSB service settinss (https://upgrade-fbs.ddbcms.dk/admin/config/ding/provider/fbs)
    - FBS endpoint URL
    - ISIL
    - Brugernavn
    - Adgangskode
    - Vælg interesseperiode
    - Enable reservation deletion
    - Disable insterest period
    - Search brances blacklist
        - Liste med brances
    - User bances blacklist
        - Liste med brances
    - Holdings brances blacklist
        - Liste med brances
- Ding provider (https://upgrade-fbs.ddbcms.dk/admin/config/ding/provider)
    - Delete provider users that are inactive for (none|1y|2y|3y|4y|5y)

### Mellemværender (Betaling via DIBS)

- Indstillinger (https://upgrade-fbs.ddbcms.dk/admin/config/payment/ding_dibs)
    - Terms of sale
    - Kreditkort typer
    - Slet transaktioner ældre end: none|30d|90d|1y

- Notifikation til webmaster (https://upgrade-fbs.ddbcms.dk/admin/config/payment/ding_dibs/emails)
    - Cron daglig afvikling på dato
    - e-mail-adresser der skal adviseres ved problemer
        - Udestående: definér problemer

- Rapporter (https://upgrade-fbs.ddbcms.dk/admin/config/payment/ding_dibs/reports)
    - Order ID
    - Transaction ID
    - Dato
    - Bruger
    - Tekst
    - Beløb
    - Cleared true/false
    - Paid true/false
    - Captured true/false

## User profile


## Globale funktioner

### Youtube nocookie
- Youtube URL'er til https://www.youtube-nocookie.com

### Webtrekk - Statistik

Opmærkning af elementer der skal trackes af Webtrekk.

- Webtrekk (https://upgrade-fbs.ddbcms.dk/admin/config/ding/webtrekk)
    - TagIntegration Domain [string]
    - TagIntegration ID [integer]

### BPI
- Serviceindstillinger (https://upgrade-fbs.ddbcms.dk/admin/config/bpi/settings)
    - Biblioteksnummer
    - WS URL
    - Key (Secret)
    - Public key
- Indholdstilknytning (https://upgrade-fbs.ddbcms.dk/admin/config/bpi/content_mapping)
    - Indholdstype (Nyhed|Bibliotek|Campaign|Campaing PLUS|E-resurse|Grupper|Nyhed|Panel|Rolltab|Side|Webform)
    - Titel
    - Resumé (Body|Fax|Lead|Phone|Slug|)
    - Brødtekst (Body|Fax|Lead|Phone|Slug|)
    - BPI tags (Body|Fax|Lead|Phone|Slug|)
    - BPI materials (Body|Fax|Lead|Phone|Slug|)
    - Syndication settings (Inkludér tags på syndikeret artikel)

### Adgangsplatformen (https://upgrade-fbs.ddbcms.dk/admin/config/ding/auth)
- Client ID
- Client secret
- Omdirigér til URL
- Authorization service
- Access token service
- Resource end-point
- Log ud

## Integrationslag (API'er og abstraktionslag)
- Databrønd
- Bibliotekssysmtem
- Billetsystem
- Betaling (Mellemværender)
- BPI (CMS Content service / BPI service)

## Campaign PLUS (https://upgrade-fbs.ddbcms.dk/admin/config/ding/campaigns_plus)

- Vægt
- Facets
- Auto generated campaigns
- Facets
- Object view
- Søg
- Notification scan interval
- Campaign cache expire

**.facetResult.facet.facetTerm.facet

## Ding DDBasic opening hours (https://upgrade-fbs.ddbcms.dk/admin/config/ding/ddbasic-opening-hours)

- Extended title
- Expand settings

Mangler afklaring: Hvad benyttes denne funktion til?

## Ding mobile search - eksport til CMS Content service (https://upgrade-fbs.ddbcms.dk/admin/config/ding/mobilesearch/content-export)

- List node typer (Checkmark til markering af eksport vises på alle valgte indholdstyper)

## Oversættelser

- Localization server
- Context på alle oversættelser (Skal tilføjes til Code guidelines)

## DDB Architecture

![Search result](http://www.plantuml.com/plantuml/proxy?cache=no&fmt=svg&idx=0&src=https://raw.githubusercontent.com/danskernesdigitalebibliotek/ding3/master/PlantUML_sequence-diagrams/search/search-field-and-autocomplete.puml)

## Ding consent (https://upgrade-fbs.ddbcms.dk/admin/config/ding/consent)

Mangler afklaring

## References

- PlantUML Sequence diagram - http://plantuml.com/sequence-diagram
- Gherkin syntax - https://cucumber.io/docs/gherkin/reference/
- Table to markdown generato - https://www.tablesgenerator.com/markdown_tables#
- User story functional specification - http://www.its-all-design.com/an-agile-functional-specification/
- PlantUML reference guide - http://plantuml.com/guide
- Plantuml Archimate sprites - http://plantuml.com/archimate-diagram
- PlantUML editor - https://www.planttext.com/
- PlantUML source code - https://github.com/plantuml/plantuml/tree/master/src/sprites/archimate
- PlantUML Arhcimate Macros - https://raw.githubusercontent.com/ebbypeter/Archimate-PlantUML/master/Archimate.puml

## Forslag til eksterne services

- Terms of use texts service
    - Samtykke (https://upgrade-fbs.ddbcms.dk/admin/config/ding/consent)
    - Cookies (?)
    - GDPR (?)

## Forslag til nedprioritering af funktionalitet

Mangler afklaring:

- Dynamic backgrounds (https://upgrade-fbs.ddbcms.dk/admin/config/user-interface/backgrounds/)
- Ding interaction (https://upgrade-fbs.ddbcms.dk/admin/config/ding/interaction)
- Place2book migration to new api (https://upgrade-fbs.ddbcms.dk/admin/config/ding/place2book/migrate)