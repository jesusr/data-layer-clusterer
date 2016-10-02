Data Layer Clusterer Plus – A(nother) Google Maps JavaScript API utility library
==============

A Google Maps JavaScript API v3 library to create and manage per-zoom-level clusters for large amounts of data layer features.

Based on [Data Layer Clusterer](https://github.com/nantunes/data-layer-clusterer) by Nelson Antunes, also based on [Marker Clusterer – A Google Maps JavaScript API utility library](https://github.com/googlemaps/js-marker-clusterer) by Luke Mehe (Google Inc.).

## Getting started

First of all, the creation of a Data Layer Cluster starts with:

scope.empresaCluster = new DataLayerClusterer(options);

The options object could have the following parameters:

| name | type | default | description | required |
|---|---|---|---|---|
| map | Google Map | - | Map where the clusters and markers has to be displayed | true |
| styles | Object - Array[Object] | [] | Styles for the markers and cluster icon | false |
| gridSize | Integer | 60 |  | false |
| minimumClusterSize | Integer | 2 |  | false |
| maxZoom | Integer | null |  | false |
| className | String | 'cluster' |  | false |
| imagePath | String | 'http://google-maps-utility-library-v3.googlecode.com/svn/trunk/markerclusterer/images/m' |  | false |
| imageExtension | String | 'png' |  | false |
| zoomOnClick | Boolean | true |  | false |
| averageCenter | Boolean | true |  | false |

## License

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
