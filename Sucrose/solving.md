Solving the Structure
================
1.	Click on the Work tab in the GUI panel. Like all active GUI elements, it will change colour and become orange.
2.	Click on the arrow next to the Solve button so that it is turns orange and points upwards. The structure solution options are displayed.

>You will find a little info button in the beginning of many lines in the GUI panel. More information on the tool is available from there.

3.	Select a solution program from the dropdown menu. Depending on your computer setup, you may only see the built-in olex2.solve pro-gram, but you may also see other programs in the list, if they are present on your machine.
4.	Click Solve (or type solve) and Olex2 will attempt to solve the structure. If a structure was already present (as would be the case in a new installation of Olex2), this model will be reset. Once the structure is solved, electron density peaks (Q-peaks), are shown as brown spheres. Hover over these to see their peak height, or look at Info | Electron Density Peaks for a clickable list of the top 10 peaks. The colour intensity of these Q-peaks represents the relative intensity. The molecule of sucrose is clearly visible, along with some much weaker, spurious peaks.

>Q-peaks represent maxima in the electron density map i.e. places where the atoms are likely to be located. If the structure solution has been successful, you will probably see the whole molecule, but this is not always the case: sometimes you will only see parts of the molecule and these might be fragmented. The intensity of the spheres is scaled to the largest peak present. So the weakest peaks appear faded out. The scaling used here can be adjusted in Info | Electron Density Peaks.

5.	In the Work section there is another header tab Toolbox Work.  Select Q-Peak Intensities from the Labels menu. The relative intensities of the Q-peaks will now be displayed as labels with each atom.

>The Q-peak names also indicate the relative intensity order i.e. the most intense peak is Q1 with Q2, Q3 … etc. having less relative inten-sity. Select Toggle On/Off from the dropdown menu in Work | Tool-box Work | Labels (or press F3). At this stage it is normally more useful to see their relative intensities.

6.	Still in the Toolbox Work click on the Q square   to toggle between Q-peaks, Q-peaks with bonds and no Q-peaks (Or press  CTRL+Q re-peatedly).

>Some of the Q-peaks may not represent real atoms at this stage so don’t worry if there are unexpected bonds.

7.	The ‘structure’ can be rotated by holding down the left hand mouse button in the background of the main screen and moving the mouse.

>Since X-rays are diffracted by the electrons surrounding atomic nuclei, the larger Q-peaks will relate to heavier atom types.

8.	The next stage is to assign atoms types to the Q-peaks. Use the left hand mouse button to click on Q-peaks that you believe correspond to a particular atom type (e.g. oxygen). Selected atoms turn green.

>If the Q-peaks don’t appear to form a structure, try typing compaq -a, which will pull Q-peaks together. Clicking on centre   (top right of GUI) has the same effect.

9.	In Toolbox Work click on the relevant atom type e.g. O. These Q-peaks will change colour depending on the atom type. Carry on assigning as many Q-peaks as possible to the correct atom type; it should be possible to find all C and O atoms at this stage (although this is not always the case for every crystal structure). With atoms selected, you can also type name C to assign all selected peaks as carbon atoms. By using the UP key, it’s easy to repeat this command.

>Hovering over the atom with the mouse pointer shows the atom label e.g. O1, which takes the format of an atom type followed by a number. There are often some spurious peaks at this stage, so identify recognisable fragments rather than trying to assign an atom type to every Q-peak. Hydrogen atoms are not usually identified at this stage, since they have a very low scattering power.