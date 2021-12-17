# Hood Hunter - README

> This document describes an explorer visualization tool to support prospective home buyers in narrowing neighbourhoods for a potential home purchase created for the CPSC 547 course. 

***Hood Hunter*** is built within an Observable Notebook (https://observablehq.com/d/7cacdf357c1a5b22) and adapted into an HTML/CSS dashboard hosted as a webapp through Github at https://ivansong3.github.io/hoodhunter/. Our Notebook organization is described [below](#observable-notebook).

All HTML and CSS styling for the dashboard is our own work with the exception of the weight modal, which is obtained from [W3](https://www.w3schools.com/w3css/w3css_modal.asp). The webapp is standalone and automatically retrieves the source code from our published Observable notebook. 

The final dashboard features 4 main components: filter, map, comparison, and details. These components are combined in a single Observable Notebook and shares several mutable variables including `city_selection`, `hovered_city`, and `selected.data`. All interactive features between these components are added by our team. Each component is described separately [below](#individual-components). 

### Data Cleaning

We implement our own code in Python to clean our datasets. This process includes filtering down to data with relevant cities, remapping locations in several datasets into census subdivisions, combining datasets into a single table, aggregating data into the correct structure, and normalizing all score values. 

### Observable Notebook

Our Observable Notebook is organized with our visual components at the beginning. All internal variables, dynamic behaviour, and settings follow after. Lastly, all libraries and external APIs are included at the end. 

### Individual Components

#### Filter

Our filter is implemented using the crossfilter from the [VegaLite](https://vega.github.io/vega-lite-api/) library and adapted to meet our specifc needs. The [Towns in England and Wales](https://observablehq.com/@rcatlord/towns) Observable example implementation of the vegalite crossfilter was used as inspiration. Helper functions were implemented to interface the drop down menu for house type with the crossfilter.

#### Map

Our base map is obtained through [Leaflet](https://leafletjs.com/) using [Open Street Maps](https://www.openstreetmap.org/copyright) and uses event triggers outlined in the Leaflet API. We superimpose the map with an SVG layer that we create using [D3](https://observablehq.com/@d3), which draws circles for our neighbourhood and adjusts dynamically to user input. We also add hover tooltips using code that we designed. 

#### Comparison

Our comparison view is based upon [Lineup](https://lineup.js.org/), but is implemented by our team exclusively since the Lineup API did not meet all of our needs. This view is created using a stacked bar chart based on a static Observable [example](https://observablehq.com/@d3/stacked-horizontal-bar-chart) with D3 but re-implement by our group. We also add hover effects, re-sorting, and weight adjustments developed by our team. The entire *favourites* functionality (drawing stars, adding effects, and filtering) is created by our team. 

#### Details

Our details view is implemented using native [Observable plotting features](https://observablehq.com/@observablehq/plot) and [Line Chart](https://observablehq.com/@d3/line-chart) to create the appropriate histograms and line chart. Highlighting and hover tooltip effects are added by our team. The line chart was also customized to plot points and dotted lines to clearly visualize missing data. We also added code to organize the charts, display scores, and display city name. Helper functions were also created to adjust the data dynamically to the housing type and the neighbourhood chosen. 

