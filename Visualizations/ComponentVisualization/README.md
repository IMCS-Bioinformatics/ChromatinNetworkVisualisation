# Component visualization
This is the component visualization.\
Components are defined in Viksna et al. Topological structure analysis of chromatin interaction networks. BMC Bioinformatics 20 (Suppl 23), 618 (2019). https://doi.org/10.1186/s12859-019-3237-z

Currently 2 datasets with pre-processed files are available:\
-Jung: Jung, I. et al. A compendium of promoter-centered long-range chromatin interactons in the human genome. Nat Genet 51, 1442–1449 (2019)\
-3DIV: Kyukwang Kim et al. 3DIV update for 2021: a comprehensive resource of 3D genome and 3D cancer genome, Nucleic Acids Research, Volume 49, Issue D1 (2021)
## How to open
To launch the visualization only the html file and a zip file containg data is necessary. Open the html file in a browser and load data using the “Browse” button on the left. This visualization has been tested on Google Chrome 112, Firefox 111 and Microsoft Edge 112.\
Note: It is normal for a network error to appear before loading the zip file. This is because there is another way to launch the visualization using a web server which loads the dataset selected in dropdown menu automatically.
![crossfilter](https://user-images.githubusercontent.com/82528920/232642390-2e035294-08be-4149-81be-703afd0aeb09.png)
## What is shown in the visualization
The visualisation consists of two parts – a crossfilter and a graph view. The crossfilter shows general information about connected components that are present in some tissue types but not in others (further called simply components). The data is summarized in pie and bar charts, each of which shows the number of components in a certain group (e.g., the significance score chart shows that the most common significance score for components that fit the selected filters is 3, and about 140 components have this score). To select some subset of data, select a part of any shown chart. In the image components with significance score of at least 3 and for which about 5-30% of nodes have proteins are selected.\
1 – Load data using dropdown options (only works when using a web server).\
2 – Load data from zip file.\
3 – View graphs of components matching selected filters.\
4 – Reset crossfilter – clear the filters you have selected in the crossfilter.\
5 – Type “A” tissues – tissues in which most (in our data at least 75%) but not all the interactions in the component are present.\
6 – Type “B” tissues – tissues in which few (in our data no more than 25%) of the interactions in the component are present.\
7 – Base tissues – tissues in which all the interactions in the component are present.\
8 – Number of vertices (chromatin segments) in the component.\
9 – Number of edges (chromatin interactions) in the component.\
10 – Significance score, a value which is calculated using the number of type “B” tissues and type “A” and base tissues in the component. Components with large numbers of these tissues have higher scores.\
11 – Proportion of component nodes (chromatin segments) where at least one gene is expressed.\
12 – Proportion of component nodes (chromatin segments) where at least one protein is present.\
13 – Average number of TADs that nodes in component base tissues belong to.\
14 – Minimum number of unique ChromHMM annotations present in the component (associated with at least one of the chromatin segments which has an interaction) in any of the base tissues.\
15 – Maximum number of TADs between two adjacent nodes (chromatin segments) of the component in any of the base tissues.\
16 – Number of components matching selected filters, and total number of components.
![component](https://user-images.githubusercontent.com/82528920/232642900-d572a95f-ed8f-4d7e-9828-c5ec7cf62da1.png)
17 – Component matching selected filters. Nodes represent chromatin segments and are shown in the order of their coordinates. Distances between two adjacent nodes show the distance between corresponding loci. Shape of the nodes shows presence of genes and proteins – circle for neither, hexagon for genes, and square for chromatin segments that have both genes and proteins. Colour shows how many ChromHMM annotations correspond to a node – blue for 0, bright yellow for 4 or more, and other colors according to the following interpolate plasma color scheme:
![color-scheme](https://user-images.githubusercontent.com/82528920/232642990-66db4095-8044-482a-8569-99f35cc32dde.png)\
The image shows nodes with 1, 2, and 3 ChromHMM annotations.\
Graph edges show interactions. Solid edges show interactions observed in the selected tissues. Dashed and more transparent edges show interactions that are present in the component’s base tissues but not in the currently selected tissues. Hover on an edge to see a list of tissues which have this interaction.\
Thick straight colorful edges between adjacent nodes show that they belong to the same TAD. Different TADs have different colors. In the image above, nodes are distributed among 3 different TADs.\
18 – Select a tissue using the radio buttons to see all the data related to the component in the selected tissue type. Check checkboxes to see interactions present in all the checked tissues. Base tissues and the tissue selected as a radio button automatically have a checked and disabled checkbox.\
19 – Browse other components in the list of components matching crossfilter selection. Components are sorted by their significance score. It is also possible to use left and right arrow keys to browse components but thay may also change selected radio button if it is active.\
20 – View main information about the component – its number (to help you find it later if necessary), number of nodes and edges, significance score, lists of IDs of base, type “A”, and type “B” tissues, and information about ChromHMM annotations (here called states). For each ChromHMM annotation that at least one node has, is shown its proportion in component nodes and in nodes that have at least one interaction in the full data of selected tissue (base). There are also small symbols showing how much the proportions differ (larger symbols show larger proportional difference), and if the annotation is more common in the component (green diamond shape) or the full data (red circle).\
21 – Hover on a node to see more precise information about it – chromatin segment, list of genes, proteins and ChromHMM annotations corresponding to it, and TAD to which it belongs.\
22 – Change back to crossfilter view. It is also possible to switch between both views by pressing the “F” key.
