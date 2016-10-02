Data Layer Clusterer Plus – A(nother) Google Maps JavaScript API utility library
==============

A Google Maps JavaScript API v3 library to create and manage per-zoom-level clusters for large amounts of data layer features.

Based on [Data Layer Clusterer](https://github.com/nantunes/data-layer-clusterer) by Nelson Antunes, also based on [Marker Clusterer – A Google Maps JavaScript API utility library](https://github.com/googlemaps/js-marker-clusterer) by Luke Mehe (Google Inc.).

## Getting started

First of all, the creation of a Data Layer Cluster starts with:

```javascript
var newCluster = new DataLayerClusterer(options);
```

The options object could have the following parameters:

| name | type | default | description | required |
|---|---|---|---|---|
| map | Google Map | - | Map where the clusters and markers has to be displayed | true |
| styles | Array[Object] | [] | Styles for the markers and cluster icon | false |
| gridSize | Integer | 60 | Size of the space the cluster covers | false |
| minimumClusterSize | Integer | 2 | Minimun number of markers the cluster could group | false |
| maxZoom | Integer | null | Max zoom the cluster groups markers | false |
| className | String | 'cluster' | Name of the class the cluster icons DOM element will have | false |
| imagePath | String | Url* | Image for the marker icons | false |
| imageExtension | String | 'png' |  | false |
| zoomOnClick | Boolean | true | Action for the click in cluster | false |
| averageCenter | Boolean | true | Make the cluster position center calculated between the position of the markers it groups | false |

* _Url_ http://google-maps-utility-library-v3.googlecode.com/svn/trunk/markerclusterer/images/m.png

Now we have a empty cluster, so we need to add the properties we want to manage with the cluster. The DataLayerClusterer is an extension of [Map.Data layer of Google Maps API v3](https://developers.google.com/maps/documentation/javascript/reference#Data), so we can add features in the usual way:

```javascript
          newCluster.addGeoJson(featureColl, {
            idPropertyName: 'id'
          });
          newCluster.setMap(scope.map);
```

## Methods

| name | type | default | description | required |
|---|---|---|---|---|
| setVisible(v:Boolean) | Set visible or hidden all the properties and cluster |
| redraw() | Redraw all the clusters |
| getTotalClusters() | Length of the created clusters array |
| getExtendedBounds() | Bounds for the area with the full DataLayerClusterer objects |
| remove(feature:Feature) | Remove the feature that corresponds with the parameter (type Feature) |

## Events

The event management could be done out of the library:

```javascript
          var eventHoverIn = scope['newCluster']._dataLayer.addListener('mouseover', function(event) {
            // Anything
          });
```

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
