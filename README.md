# Alkimia GeoNode Tools
 A repository of Geo Node Tools created during, in and for the Alkimia Project

All files and sub-projects of the Alkimia project are released under both CC-NC and CC-BY.
Both are valid licenses to use this content under.


## Motion Graphics
![[https://youtu.be/dIZ4FRF1pDY]]
!! Warning: This is a WIP and many Node Groups's functionality and names are being changed per version!!
There are also a lot of Deprec nodes in v001.
Nodes are also not documented yet (working on it!)

### Goals:
Motion Graphics in this toolset focuses on facilitating a number of concepts:
1. Interacting with objects as instances
2. Mapping between objects/domains for matching IDs
3. Naming of objects in domains via strings -> Ints
4. Converting between local/global/custom spaces and l/g/c/instance spaces
5. Standard pre-at-post processing geometry
6. Collections as layer sources using standard pre-at-post processing
7. Aligning instances to controllers
8. Randomized Variation of Anim Curves at at sample time
9. Splitting assets into instances with IDs

### Process:
The general flow of the example shown is:

#### Prep:
0. Append 'Store' Node Tree from release file to current file

1. Link Source Asset (see attributions below!)
2. Generate split and aligned Instances 
	- See '0. Prep Assets' on objects in Orig_Asset Collection
	- A script is used to fill out ID using mesh name.
	- Objects are aligned to Inst_Target in example with axis flattened (see GN Tree)
3. Link Objects (and instances) into collections by layer

1. Create Anim Curves, attach information
	- See '0. Curve_Preprocesser_Graph' on Timing_Curve_1 in FX_Curves Collection
	- A script is used to fill out ID using mesh name.
2. Create Motion Curve

1. A mesh to process everything inside of
	- See Anim_With in example

#### Application
Per layer:
1. Reference and clean Layer Src collection
2. Preprocess Instances
3. Process Instances
4. Store Str -> Ints of Target MC, Anim
5. Reference Cleaned Curves
6. Map indices of curves to Instances by matching target ID
7. Realize Motion Curve
8. Sample Anim Curve
	- Randomness from curve settings is used in application
	- Inserting remapped Instance's local space Z from Controller as factor
9. Sample Motion Curve By Anim Curve Result

## Attributions:
### MotionGraphics:
	The source model used in Test_Asset (and by extension v001) was created by:
	https://x.com/ChengduLittleA
	and was retrieved from the blender foundation at:
	https://cloud.blender.org/p/gallery/608da4565f9fe397b1944ba2
	Released under a CC-BY License