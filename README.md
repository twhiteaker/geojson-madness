GeoJSON Geoprocessing Tool for ArcGIS
=

GeoJSON is some new upstart format that's come around in the past few weeks. Here's a set of tools to get GeoJSON in/out of ArcGIS.

Usage should be self-explanatory: open up the toolbox in ArcCatalog/ArcMap, select your features to export or import, and there you go. Easy in/out of most GeoJSON you'll find out there on the internet.

This tool _always_ exports to WGS 1984, because most people on the internet shuffling GeoJSON around are barbarians who don't know the first thing about spatial reference systems*. The same applies for import, right now it assumes coordinates are all in WGS 1984.

\* This is tongue-in-cheek, you guys. Who outside of the geospatial professions knows about this stuff? Or even needs to? Some software developer who found a GeoJSON Gist on GitHub just wants to look at it on a map without needing to take a semester long course to understand the theory behind the dang coordinate  pair numbers in the dang data that's just dang old sitting there.

Theoretically Asked Questions (TAQ)
-

_Nobody has asked me these yet, but these are the questions I anticipate coming up at some point. Now you don't need to ask them. You're welcome, I've just saved both of us some time._

1. **What is this?**

    This conversion tool is meant to do one thing quickly, smoothly, and well. I have a feature layer in my ArcMap table of contents I want to make into GeoJSON. I have GeoJSON somewhere on the internet and want a feature layer in my table of contents to do some geoprocessing on. Ok. Here you go. Do it with this tool.

2. **Why GeoJSON?**

    GeoJSON is a format that is obviously missing from the ArcGIS stack. I wanted to provide a stupidly easy way of getting this format in and out so we could all go back and live our lives without the specter of "well what about GeoJSON???" hanging over us.

3. **Why not other formats like WKT or WKB?**

    As of 10.1 SP1, `arcpy.da` cursors have `SHAPE@WKT`/`SHAPE@WKB` tokens, and `arcpy` geometry has `.WKT`/`.WKT` attributes, and the `arcpy.FromWKT` and `arcpy.FromWKB` functions, and as of 10.2 you can make SpatialLite databases and they even show up in the ArcCatalog window with all their feature classes. So there's enough other open formats already there and ready to go. GeoJSON's mostly just to fill the lightweight-data-shuffled-over-HTTP niche.

4. **What about [Esri2Open](https://github.com/project-open-data/esri2open)? Doesn't that accomplish the same goals?**

    I was not aware that project existed until after I'd written this. Esri2Open seems to be quite a bit more ambitious with what sorts of format it supports and what it does (merge/append) and is therefore quite a bit more complex. Some of the formats it does like the aforementioned WKT and WKB are trivially handled by ArcGIS' Python functions in new versions of ArcGIS so I fail to see the utility except as a stopgap for users on 10.0 waiting to upgrade to 10.1 or 10.2.

License
-

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this project except in compliance with the License. You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.



