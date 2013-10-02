# Twinned Structures
## Twinning
Twinning in crystallography means that the crystal contains more than one domain related by a symmetry operation, consequently the diffraction pattern measured is a combination of the diffraction patterns from each of the domains. Twinning makes the data analysis more complicated but with advances in computing and software it is normally possible to resolve twinned crystals. A good introduction to twinning can be found in S. Parsons, (2003), ActaCryst., D59, 1995-2003.
### Common signs
There are a number of warning signs for twinning that have been identified, not all will exist at any one time, but if signs are present it is worth investigating twinning. The following list is derived from a list published in R. Herbst-Irmer& G. M. Sheldrick, (1998), ActaCryst., B54, 443-449, where applicable suggestions of where to check features within Olex2 are highlighted: 
- Indexing problems:
-- Difficulty obtaining a cell.
-- An unusually long axis.
-- Split reflections.
- Rint for a higher symmetry group is similar to that of the low symmetry group.
- The metric symmetry is higher than the Laue symmetry of the dif-fraction pattern e.g. a monoclinic structure with �~90.0� appears orthorhombic.
- Problems identifying the space group either the systematic absences are not consistent with a space group or it is uncommon. (To examine this in Olex2 Work | Solve | Suggest SG, the output will be displayed on the screen (and in your text editor after clicking on the notepad icon.) 
- The average value of |E2-1| is lower than expected the expected values. (Two graphs in Olex2 can assist with assessing this under Info | Reflection Statistics there are the options to plot the Cumulative In-tensity Distribution and the Wilson Plot also has an assessment of the average |E2-1| value for the structure below it).
- The structure cannot be solved.
- The refinement is unsatisfactory:
-- Fo>>Fc for the majority of the most disagreeable reflections. Dis-agreeable reflections can be omitted under Info | Bad Reflections and clicking on omit. In addition under, Info | Reflection Statistics a plot of Fo �Fc should have a gradient of ~1 and an intercept ~0, without many reflection deviating from this line, any reflections that have been omitted will be greyed out, while Fo/Fc versus resolution should have a value of ~1.
-- R1 and wR2 remain unexpectedly high based on the Rint value. Generally the R1 value should be approximately similar to the Rint upon completion, see Info | Refinement Indicators and Info | Reflection Statistics Summary.
-- Weights the second value of the weighting scheme remains very high e.g.> 5, to check this see Work | Refine | Weights.
- Higher symmetry crystal systems in the lower symmetry Laue classes are often subject to merohedral twinning so this is always worth checking. Possible twin laws can be searched for under Tools | Twinning | Search for Twin Laws.
The first 3 points on the list above should be assessed within the data processing software. The remaining points can be checked within Olex2. 
### Treating twinning
Olex2 can automatically search for twin laws and suggest any likely twin laws or you can input twin laws to test. There are different types of twinning: 
#### Merohedral and psedudo-merhohedral Twinning
Those where the reciprocal lattices (i.e. reflection positions) exactly overlap which is known as twinning by merohedry or pseudo-merohedry this is relatively simple to treat and procedures are described below. In the case of merohedral or pseudo-merohedral twinning a twin law and twin scale factor are added to the head of the .ins file below the unit instruction in the form
TWIN -1 0 1 0 -1 0 0 0 1 2
BASF 0.1
Where -1 0 1 0 -1 0 0 0 1 2 is a 3 by 3 matrix to define the twin law 2 is the no. of twin components. BASF is the twin scale factor, an arbitrary value < 1 is selected which is subsequently refined
#### Non-merohedral twinning
Non-merohedral twinning where only some of the reflections overlap are more complicated and require the preparation of a different type of .hkl file (an HKLF 5 file) prior to refinement within Olex2. A BASF ## (where ## is an arbitrary number <1) line is included in the .ins file, but no TWIN law.
Only one twin law can be applied to the data at any time (with the exception of including racemic twinning alongside a twin law). Any twin laws that are being applied to the data are displayed below the refinement statistics at the top of the GUI panel . 
### For merohedral and pseudo merohedral twins
Automatic searching for twin laws � this can be done using Olex2, Tools | Twinning | Search for Twin Laws, the program searches for metrically possible twin laws, if found the structure is refined against each of them in turn. The R value gives an indication of the quality of the structure, a low R value is better. To select a twin law to continue the refinement click on the relevant twin law.
If a twin law is selected Olex2 automatically includes the selected twin law and BASF into the .ins file. The matrix (1 0 0 0 1 0 0 0 1) is the untwined refinement. BASF is the twinned scale factor indicating what percentage of the structure would be the second component i.e. 0.20 (=20%) would suggest 80% is component 1 and 20% is component 2. Currently it is only possible to refine using one twin law (excluding racemic twinning) in Olex2.
Manually entering a twin law � click on editins   to view the top of the .ins file. Somewhere below the UNIT instruction type TWIN followed by the twin law e.g. TWIN -1 0 1 0 -1 0 0 0 1 2 and type BASF followed by some value <1. 
Racemic twinning � Click on editins   to view the top of the .ins file. If a twin law is not included add TWIN on one line and BASF 0.2 on the second line. If a twin law is already included e.g. TWIN -1 0 1 0 -1 0 0 0 1 2, change 2 to -4 (calculates racemic twinning component for component 1 and component 2 giving 4 components) and add two randomly selected numbers <1 (~0.1 is sensible) to the BASF line which will give the fraction of each component.
Racemic twinning is only applicable in non-centrosymmetric space groups. If the BASF refines to some very small number or >1 the twin law is not valid and should be removed. It is possible to return to the original structure Tools | Twinning and select the original matrix (1 0 0 0 1 0 0 0 1) or use the Work | History function.
Non-merohedral twins � Using an HKLF 5 file � click on the editins   to view the top of the .ins file. Somewhere below the UNIT instruction type BASF ## followed by some value <1. Ensure that MERG is set to 0 and that HKLF is set to 5 at the bottom of the .ins file