## Introduction

Thinking Machines Data Science is releasing TM Open Buildings, a dataset of manually-drawn building outlines covering 12 Philippine cities with detailed annotations on building and roof attributes as seen over satellite imagery. We contribute the buildings in OpenStreetMap and also made available for download in Kaggle. This is made possible with the support from the [Lacuna Fund](https://lacunafund.org/).

Kindly use the [**Issues tab**](https://github.com/thinkingmachines/ph-open-buildings/issues) to file any specific concerns about the dataset.

## License
This TM Open Buildings dataset is made available by Thinking Machines under the [Open Database License](http://opendatacommons.org/licenses/odbl/1.0/). Any rights in individual contents of the database are licensed under the [Database Contents License](http://opendatacommons.org/licenses/dbcl/1.0/).

## Building Definitions
We define the buildings we mapped, as well as the attributes included, in the table below. Please refer to our [wiki page](https://wiki.openstreetmap.org/wiki/TM_Open_Buildings) for more details.
| Building Type  |Subtype        | Definition                                                                             | Mapped Attributes                                       |   
|----------------|--------|----------------------------------------------------------------------------------------|---------------------------------------------------------|
| Settlement     | Single | Residential houses that are individually distinct from surrounding structures          | Roof material, Roof layout, Is within gated community?  |   
|                | Dense  | Tight clusters of small residential houses that do not have distinguishable boundaries | -                                                       |   
| Non-settlement |        | Commercial, industrial, or institutional buildings                                     | Building height                                         |   

## Coverage
The dataset covers selected 250m x 250m tiles in 12 Philippine cities, namely Dagupan City, Palayan City, City of Navotas, City of Mandaluyong, City of Muntinlupa, Legazpi City, Tacloban City, Iloilo City, Mandaue City, Cagayan de Oro City, Davao City, and Zamboanga City. The tiles are chosen to focus on residential areas that lie on a wide variety of terrains (urban, coastal, riparian, agricultural, etc.). All settlements and non-settlements within each tile are drawn manually. Data on the locations of the tiles are given in the following [table](https://docs.google.com/spreadsheets/d/1jLoGUtnd1qyvqN43uQEtCo0C4x2QR3DkSKolH2ep_uU/).

## Attributes
The following table contains the definitions of the attributes and how it is tagged in OSM.
| Attribute              | Type                               | Characteristics                                                                                                                                                                                | OSM Key and Tag                               |
|------------------------|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Roof Material          | Natural/Galvanized Iron (GI)/Mixed | Looks rusty when old, silver/gray when new, lines and patches are usually evident.                                                                                                             | `roof:material = metal_sheet`                    |
|                        | Metal/Tiled                        | Whole roof is usually one solid color, tiled roofs have texture.                                                                                                                               | `roof:material = roof_tiles`                     |
|                        | Concrete                           | Flat, usually has raised white edges, no visible roof “folds”, may be smooth or have objects on top.                                                                                           | `roof:material = concrete`                      |
| Roof Layout            | Single Layer Basic                 | No complex architecture. Plain flat or rectangular roof. At most 4 faces are visible. 1 single layer visible.                                                                                  | `roof:shape = gabled  `                          |
|                        | Single Layer Intricate             | Complex shapes on rooftop and multiple vertices, more than 4 faces visible, but still 1 single layer.                                                                                          | `roof:shape = hip-and-gabled`                    |
|                        | Multilayer                         | One roof on top of another. A shadow separating the rooftops is seen.                                                                                                                          | `roof:levels = 2`                                |
| Within gated community |                                    | Uniform roof and lot sizes, structured street layout, “themed” street names, development name given in address                                                                                 | `residential = gated`                           |
| Is a dense settlement  |                                    | Densely packed small houses with overlapping rooftops. Rooftop materials are mostly natural/light, mixed, galvanized iron (GI). Narrow one-lane streets, or no visible streets between houses. | `residential = irregular_settlement`           |
| Building height        | Low                                | 1-5 storeys                                                                                                                                                                                    | `note = ”This building has 1-5 storeys"`          |
|                        | Medium                             | 6-15 storeys                                                                                                                                                                                   | `note=”This building has 6-15 storeys"`         |
|                        | High                               | >15 storeys                                                                                                                                                                                    | `note=”This building has more than 15 storeys"` |

## Imagery
We used [Mapbox Satellite Streets](https://www.mapbox.com/maps/satellite)) imagery as of August-September 2023 to trace the building outlines and deduce roof and building attributes. This imagery is a combination of multiple global satellite imagery sources from commercial providers, NASA, and USGS, which have different capture dates. To check if the outlines in the dataset are the most updated ones in an area of interest, you may compare with another imagery source with a known capture date. 

## FAQs
#### What does the data include?
   
TM Open Buildings is a dataset of building footprint outlines of settlement and non-settlements with annotated physical characteristics as seen on satellite imagery (i.e. building and rooftop attributes).
#### What is the data intended to be used for and why is the data being released?

The data was created with funding from the Lacuna Fund as part of the datasets developed under Project CCHAIn (Climate Change, Health, and Artificial Intelligence) which aims to address the knowledge gap on health impacts from climate change for informal settlements in the Philippines. For example, overlaying this data with various hazard information such as flooding, landslides, and fault lines can bring much more granular and targeted insights to disaster risk reduction research and response.

#### How updated is the data?
   
The data was developed from August-October 2023. To support the nature of the OSM platform, we welcome users to actively participate in the continuous updating and improvement of the data based on local knowledge.

#### How can I download the data?
   
You may download in Kaggle or view the tiles in OpenStreetMap.

#### How is the data created?
   
Thinking Machines collaborated with data annotators to draw and annotate satellite imagery in select areas around the country, in line with the project’s geographical focus. These annotations were then quality checked, post-processed, and conflated by TM with any existing OSM tags before uploading on the OSM platform.

#### What is the coordinate reference system?

We used EPSG: 4326 to draw the outlines.

#### How can I use the data for a machine learning project?

You can use outlines in combination with the basemap imagery and the tile bounding boxes provided in this table to create an annotated tile that can be used to train a computer vision model. This model can detect buildings and/or assigned roof attributes on other areas we have not yet covered. 

#### Will there be more data coming for new areas?

There are currently no plans to release more data within the scope of the project, but TM is interested in continuously contributing to the OpenStreetMap community.

#### I want to add details and/or make changes. Do I need to inform Thinking Machines?

Yes, improvements to our datasets are always welcome. In accordance with OSM policies, you do not need to ask permission to modify existing data, but please keep in mind OSM’s [Code of Conduct] (https://wiki.openstreetmap.org/wiki/Code_of_conduct) and [mapping best practices](https://wiki.openstreetmap.org/wiki/How_We_Map) at all times. 

#### I know this building from our location- why does it seem smaller in your outlines?

We acknowledge this possibility. Our outlines may be smaller than the actual building because we drew outlines using the building’s roof rather than its walls or lot extent. Those are usually the same shape but there are a few cases where the roofs are smaller.

#### Why do some buildings appear misaligned from the satellite imagery?

We used a Mapbox basemap as of August 2023. While Mapbox updates its imagery, there may be instances where the images used to identify buildings are not the same as the current ones due to different timeframes of the source imagery. Additionally, when there is a sizable difference in the satellite camera vantage angle, buildings may seem to be offset compared to the current imagery.

#### Can I create a derivative dataset and release it?

Yes, the Open Data Commons Open Database License (ODbL) license allows you to use our dataset for a derivative product. However, if you create a derivative work using ODbL-licensed data, you must release that derivative work under the same ODbL license, i.e., it must also be open and share-alike.

## Legal Notices
The License granted for TM Open Buildings does not grant rights to use the name, logo, or trademarks of Thinking Machines.
Thinking Machines reserve all other rights whether under their respective copyrights, patents, trademarks, or other intellectual property, whether by implication, estoppel or otherwise.



