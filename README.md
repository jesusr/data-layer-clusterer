Data Layer Clusterer – A Google Maps JavaScript API utility library
==============

[![Join the chat at https://gitter.im/nantunes/data-layer-clusterer](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/nantunes/data-layer-clusterer?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

A Google Maps JavaScript API v3 library to create and manage per-zoom-level clusters for large amounts of data layer features.

Based on [Marker Clusterer – A Google Maps JavaScript API utility library](https://github.com/googlemaps/js-marker-clusterer) by Luke Mehe (Google Inc.).

You can find the minified JS file [in the releases tab](https://github.com/Connum/data-layer-clusterer/releases).

## About this fork

While working with the data layer feature was fun because of the simplicity of adding and getting map content via GeoJSON, I soon encountered the problem of too many markers, lines and polygons being displayed when zooming out of the map. I knew about the marker clusterer for normal layers, but it took me browsing through several StackOverflow posts and pages of search results to stumble upon nantunes' approach to data layers.

Seeing that there hadn't been any work done on the project for almost a year, I tried out jesusr's fork, which included some fixes/optimizations, but out-of-the-box it would just throw JS errors in the console. After forking it and getting it to work, I had to find out that just like the version in the initial repo, there was no support for LineStrings or Polygons, which I needed. Also, the URL to the cluster marker icons was no longer valid, so that had to be fixed as well, and so I did.

My current implementation now includes the following changes:
- Fixed cluster marker image URLs
- Added SVG versions of the marker images which will be used by default if supported by the browser and falls back to the PNG versions
- LineStrings and Polygons are being clustered as well, using the center point of their bounding rectangles
- new option 'setProperty': If set to true, instead of changing the StyleOption attribute 'visible' of the features directly, a boolean property 'in_cluster' (or a configurable property name defined in the constant DataLayerClusterer.CLUSTER_PROPERTY_NAME) is set on the features, which can then be used to toggle visibility (for example in order to take into account other properties for additonal filtering)
- new option 'recolorSvg': (string) only takes action if SVG is supported and being used: a selector string for an SVG element in the set imagePath that can be used for re-coloring the cluster marker image. This saves requests and prevents the different marker images popping up after loading.
- new option: 'minimumPolySize': (number) The minimum width or height of the bounding box of a feature (other than type 'Point') in pixels before it is forced into a cluster, even if the cluster ends up containing only this one feature. 0 or false to disable this functionality.

To read more and view a working example, see my blog post at www.constantinmedia.com/2016/09/google-maps-javascript-api-v3-handling-large-amounts-of-features-using-clustering-in-data-layers/

## More to come
- When LineStrings and Polygons are becoming too small according to the minimumPolySize option, display a marker instead for better visibility.

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
