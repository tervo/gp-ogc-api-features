# Deployments in North-Rhine Westphalia

## 1. Data provider

Datasets from multiple data providers from North-Rhine Westphalia, Germany.

## 2. Thematic scope

Currently, the following datasets are available:

* Mining permits (Bergbauberechtigungen), data theme AM
* Fire brigade control centres (Feuerwehrleitstellen), data theme US
* Child care facilities (Kindertageseinrichtungen), data theme US
* Hospitals (Krankenhäuser), data theme US
* Various agricultural datasets relevant in the context of the [Integrated Administration and Control System (IACS)](https://ec.europa.eu/info/food-farming-fisheries/key-policies/common-agricultural-policy/financing-cap/financial-assurance/managing-payments_en), data themes LC/LU
* Low emission zones (Umweltzonen), data theme AM

All agricultural datasets currently contain only a small sample of 100 features each.

In addition, extensions to the INSPIRE codelists are published in another API. This currently declares the item type as "features", but it is planned to migrate this in the future to OGC API Records.

## 3. Envisaged use

Currently, the Web APIs are under development. It it planned to move the APIs to production in 2020, hosted by [IT.NRW](https://www.it.nrw/).

## 4. Requirements classes

From the draft Good Practice:

* Requirements class "INSPIRE-pre-defined-data-set-download-OAPIF"
* Requirements class "INSPIRE-multilinguality"
  * The implementation meets the requirements, but language selection only affects text generated by the API (html and link titles), not text in the data. All text in the data is always in German.
* Requirements class "INSPIRE-OAPIF-GeoJSON"
  * There are some differences to the "INSPIRE UML-to-GeoJSON encoding rule" that we will document.
* Requirements class "INSPIRE-bulk-download"
  * This requirements class is implemented for most APIs, typically linking to a CSV file and/or Shapefile archive, but for the low emission zone dataset there is currently no such file.

The current development deployment supports the following OGC API requirements classes:

* OGC API - Features - Part 1: Core 1.0
  * Core (required by INSPIRE)
  * OpenAPI 3.0 (required by INSPIRE)
  * GeoJSON (required by INSPIRE)
  * HTML
* OGC API - Features - Part 2: Coordinate Reference Systems by Reference Release Candidate (in approval vote)
  * Coordinate Reference Systems by Reference
* OGC API - Features - Part 3: Filtering and the Common Query Language (CQL) DRAFT
  * Filter
  * Features Filter
  * Simple CQL
  * CQL Text encoding
  * CQL JSON encoding
* OGC API - Tiles - Part 1: Core DRAFT
  * Tile Set
  * Tile Sets
  * Dataset Tile Sets
  * Geodata Resource Selection
  * Geodata Resource Tile Sets
* OGC API - Tiles - Part 2: Tile Matrix Sets DRAFT
  * Tile Matrix Sets
* OGC API - Styles DRAFT
  * Core
  * HTML
  * Mapbox Styles
  * Queryables
  * Style Info
  * Resources (only, if the style needs symbols)

## 5. Server-side technology

The development deployment uses [ldproxy 2.0](https://github.com/interactive-instruments/ldproxy). ldproxy is available under the Mozilla Public License 2.0.

The production deployment will use XtraServer Web API, which integrates ldproxy.

## 6. Endpoints and client applications

Landing page of the deployment: https://inspire-nrw.ldproxy.net/

APIs:

* Mining permits (Bergbauberechtigungen): https://inspire-nrw.ldproxy.net/bergbau/v1
* Fire brigade control centres (Feuerwehrleitstellen): https://inspire-nrw.ldproxy.net/feuerwehr/v1
* Child care facilities (Kindertageseinrichtungen): https://inspire-nrw.ldproxy.net/kindergarten/v1
* Hospitals (Krankenhäuser): https://inspire-nrw.ldproxy.net/krankenhaus/v1
* Agricultural datasets:
  * https://inspire-nrw.ldproxy.net/bena/v1
  * https://inspire-nrw.ldproxy.net/ble/v1
  * https://inspire-nrw.ldproxy.net/blehist/v1
  * https://inspire-nrw.ldproxy.net/ccwas/v1
  * https://inspire-nrw.ldproxy.net/ccwind/v1
  * https://inspire-nrw.ldproxy.net/dgl/v1
  * https://inspire-nrw.ldproxy.net/fb/v1
  * https://inspire-nrw.ldproxy.net/le/v1
  * https://inspire-nrw.ldproxy.net/oevf/v1
  * https://inspire-nrw.ldproxy.net/topup/v1
  * https://inspire-nrw.ldproxy.net/ts/v1
  * https://inspire-nrw.ldproxy.net/tshist/v1
  * https://inspire-nrw.ldproxy.net/udgl/v1
  * https://inspire-nrw.ldproxy.net/umwe/v1
  * https://inspire-nrw.ldproxy.net/zfga/v1
  * https://inspire-nrw.ldproxy.net/zfum/v1
* Low emission zones (Umweltzonen): https://inspire-nrw.ldproxy.net/luftreinhalteplan/v1
* INSPIRE-Codelist extensions: https://inspire-nrw.ldproxy.net/codelist/v1

## 7. Issues

All issues with respect to the requirements in the Good Practice document were discussed and addressed in the [meeting on 4 September 2020](https://github.com/INSPIRE-MIF/gp-ogc-api-features/blob/master/action%202020.1/meetings/progress%20meeting%20040920207/minutes.md) and the associated [pull request](https://github.com/INSPIRE-MIF/gp-ogc-api-features/pull/63).

In the bigger picture, it would be good, if other INSPIRE service types could also be provided using current Web APIs. For example, see the issue on [INSPIRE View Services](https://github.com/INSPIRE-MIF/gp-ogc-api-features/issues/37).
