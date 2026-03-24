# Jakarta Origin Destination Analysis
Analysis of human movement in kelurahan level in Jakarta based on gravity model.
## Background
This project happened because of author curiosity toward public transportation development topic. The interest came after exploring other advanced countries, Japan and Hong Kong. It was fascinating to see small city outside Tokyo, Kamakura, who has a good transportation system according to my personal observation. It all connected from city center (in this case Kamakura station) and it feels all the regions are easy to access even by tourist.

# Theory
Gravity Model to determine number of flow from origin to destination area.


$$T_{ij} = \frac{P_i^{\alpha} \times A_j^{\beta}}{d_{ij}^{\gamma}}$$

| Symbol | Parameter | Value | Description |
|--------|-----------|-------|-------------|
| $T_{ij}$ | OD Flow | — | Estimated trips from zone $i$ to zone $j$ |
| $P_i$ | Population | — | Population at **origin** zone $i$ |
| $A_j$ | Attractiveness | — | POI count at **destination** zone $j$ |
| $d_{ij}$ | Distance | — | Euclidean distance between zone $i$ and $j$ (metres) |
| $\alpha$ | Alpha | 1.0 | Population exponent |
| $\beta$ | Beta | 1.0 | Attractiveness exponent |
| $\gamma$ | Gamma | 2.0 | Distance decay exponent |

The model represents:
1. The higher value of population and attractiveness lead to higher estimated travels.
2. While greater the distance between population (i) and attractiveness (j), fewer estimated travels.
3. $\alpha$, $\beta$, and $\gamma$ are components to define whether the variables are significant or not.

# Data Collection
I used 2 data resource, administrative boundaries (kelurahan level) and Point of Interest (POI) from each administrative boundaries.
1. Administrative boundaries: https://data.humdata.org/dataset/cod-ab-idn
2. Point of Interest (PoI): library osmnx with tags

| OSM Key | OSM Values | Description |
|---------|------------|-------------|
| `office` | `True` | All office types |
| `amenity` | `school`, `university`, `hospital`, `marketplace` | Public facilities |
| `shop` | `mall`, `supermarket`, `department_store` | Retail & shopping |
| `building` | `commercial`, `office`, `retail` | Commercial buildings |

# Result

Top number of PoI in kelurahan level
  1. Kuningan timur
  2. Gambir
  3. Kebon Melati
  4. Cikini
  5. Menteng
     
![](https://github.com/RodzanIskandar/Jakarta-Origin-Destination-Analysis/blob/main/outputs/top_poi_count.png)
![](https://github.com/RodzanIskandar/Jakarta-Origin-Destination-Analysis/blob/main/outputs/top_destinations.png)
   
   
