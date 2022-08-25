# Carceral PFAS Analysis

## About

The code and data in this repo calculates the number, percentages, and populations of US carceral facilities in the same HUC-12 watershed boundary and, as a proxy for hydrologic flow, at a lower elevation than point sources with likely PFAS contamination.

## Contributors

<!-- ALL-CONTRIBUTORS-LIST:START -->
| Contributions | Name |
| ----: | :---- |
| [🔢](# "Data") [💻](# "Code") [🤔](# "Ideas and Planning")| [Lindsay Poirier](#) |
| [🔢](# "Data") [🔬](# "Research") [🤔](# "Ideas and Planning") | [Derrick Salvatore](#) |
| [🔬](# "Research")  [🤔](# "Ideas and Planning") | [Phil Brown](#) |
| [🔬](# "Research") [🤔](# "Ideas and Planning") | [Alissa Cordner](#) |
| [🔬](# "Research")  [🤔](# "Ideas and Planning") | [Kira Mok](#) |
| [📋](# "Organizer")[🔢](# "Data")[🔬](# "Research")[🤔](# "Ideas and Planning") | [Nicholas Shapiro](https://github.com/shapironick) |

<!-- ALL-CONTRIBUTORS-LIST:END -->

(For a key to the contribution emoji or more info on this format, check out ["All Contributors."](https://allcontributors.org/docs/en/emoji-key))

## Repo Architecture

There are two R Markdown files in this repo:

1. get_HUC_elevation.Rmd
  * Imports source datasets and transforms them to a common CRS (4269)
  * Calculates the total facilities under consideration each category
  * Determines which watershed boundary (HUC-12) each facility in the source datasets geo-spatially intersect with
  * Determines the elevation of each facility in the source datasets via the USGS Elevation Point Query Service
  * Saves the resulting data as .gpkg files for use in HUC_analysis.Rmd
  
2. HUC_analysis.Rmd
  * Loads the .gpkg files created in get_HUC_elevation.Rmd
  * Joins carceral facility data to data representing the locations of each potential point source based on a shared HUC-12 code
  * Filters to carceral facilities at a lower elevation than a potential point source as a proxy for hydrological flow direction
  * Calculates the number of unique facilities in the same HUC-12 watershed boundary and at a lower elevation than each point source and a combination of point sources, along with the number of incarcerated people potentially impacted
  * Produces the tables and plots presented in the manuscript
  
Please reach out for source datasets

## Notes

* As of 2020, US facilities were required to report certain PFAS emissions via the Toxic Release Inventory (TRI). This past year 39 facilities reported PFAS emissions to the TRI. When we looked into these facilities, and the changes to the results of the analysis were negligible. We opted to exclude this category based on concerns that the novelty of this reporting requirement was resulting in dramatic under-estimations of the total emitted PFAS. 
* Carceral facilities reported by HIFLD are missing a number of private and ICE facilities. Population data is also missing for about 29% of these facilities. 

## Copyrights

All code in this repo is licensed with a GNU General Public License 3.0. Please see the [license](https://github.com/Critical-Data-Analysis-Group/Carceral-PFAS-Analysis/blob/main/LICENSE) file for details.

All written materials are licensed with a Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0). Please see this [license](https://creativecommons.org/licenses/by-sa/3.0/) for details.

## Have Questions?

Contact [Lindsay Poirier](mailto:lpoirier@smith.edu)

