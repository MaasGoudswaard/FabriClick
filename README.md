# FabriClick: Interweaving Pushbuttons into Fabric Using 3D Printing and Digital Embroidery
Presenting a new way to seamlessly integrate tactile pushbuttons into fabrics to enable eyes-free inputs on soft wearables!  
This is the repository from the DIS2020 Pictorial. Here, you can find the files to fabricate your own FabriClick (with detailed instructions below!)
Pictorial: https://doi.org/10.1145/3357236.3395569
You can also watch the video: https://www.youtube.com/watch?v=m9yXMVoc-N0&feature=youtu.be

# Fabricating the FabriClick
All files referenced below can be found in the repository files.

## Tools and Machines Necessary for Fabrication:
1. Digital embroidery machine, with a 180mm x 130mm embroidery frame workspace (We utilised the Brother 655 machine, but feel free to try out new machines!)
2. FDM 3D printer (ie. Creality Ender 3)
3. Lasercutter

## Materials Needed:
1. Flexible filament (ie. Tronxy TPU with a 95A Shore Hardness)
2. Conductive yarn (ie. HC 40 conductive thread by Madeira)
3. Flexible fabric (ie. a nylon lycra blend)
4. Copper pads
5. Copper coil wire
6. Small crimps
7. Microcontroller (ie. Arduino UNO)
8. Bulldog foldback clips
9. M3/M4 Nuts and bolts
10. 8mm thick acrylic
11. 180mm x 130mm embroidery hoop

## Assembly of the frame
Prepare the parts by lasercutting the “Frame Design V3 Drawing.DXF” design from a
First the frame system has to be prepared, "Frame design V3 drawing.DXF" has to be cut by a lasercutter in 8MM thick acrylic sheet. 
The baseplate needs to be assembled as illustrated in the pictorial. The baseplate can be screwed together with M4 bolts. Take off the 180 * 130 embroidery frame connectors and attach them to the lasercut frame use M3 bolts to connect them all together, it might be necessary to drill out the holes.

## Calibration
### Embroidery Machine
After the assembly of the frame the embroidery frame should slot into the Brother machine. Make sure the bolts are tight and will not move when the machine is operating. Take the "Calibration square embroidery.ai" file, save it as WMF or other and make sure the pattern is auto-centered on the machine. Attach a lycra fabric sheet to the embroidery frame with the bulldog clips, make sure it is in a tense state. Embroider the calibration square onto the lycra fabric, with a non-conductive yarn.
Use large bulldog clips to attach the baseplate to the 3D print bed, such that it can move freely. Then first insert the embroidery frame into the 3D print frame, then insert the two with the connectors facing DOWN. Ensure both frames fit tightly within the jig by adjusting the 4 corners.
### 3D printer
Turn on the 3D printer and calibrate the Z-axis such that it prints onto the embroidered cross, it is wise to create a new custom "printer" within your slicer program. Make the build-plate surface 140 * 190 mm, to ensure you will not hit the edges of the embroidery frame. Process and print the "Calibration square printer.STL". You need not to fully print the part, use it as a guidance. You can change the position of the printed square by either changing the offset of the printhead in the slicer or moving the baseplate. It is good practise to do most digitally as you dont have a lot of space to move the baseplate within the 3D printer frame. The baseplate is calibrated when the 3D printer goes over the embroidered square.

## Fabricating the buttons
When the baseplate is properly installed the fabrication process can start.
### 3D print
Start by attaching a lycra fabric onto the 3D print frame, make sure to have as much tension in the fabric as you can while maintaining an even stretch. 3D-print "V3 3D print button.STL" onto the lycra fabric, make sure the frame is facing down and the lycra fabric facing up.
After printing small copper pads can be attached onto the underside of the 3D printed buttons, the copper pads should not be wider that the circular touchpoints.
### Embroider
Then the embroidery file has to be prepared, import the "V3 embroidery matrix.ai" into the embroidery software, there are a few different stitches which need to be sewed in different orders, note: settings can differ between thread, machine and fabric:
The red lines are conductive stitches. They need to be stitched with a 1.5mm wide zigzag stitch with a density of 1 (stitch per mm, preferably lower) WITHOUT under sewing, the conductive yarn has be be placed onto the bobbin in these stitches. In parts where the columns and rows jump over each other (where the green stitches are) the zigzag-stitches need to be removed such that the stitch is one long jump over the isolation stitch.
The Green are isolation stiches, they need to be stitched with a dense stem, with a large angle. This needs to be experimented with, the denser the better to ensure proper isolation, a thicker yarn in the bobbin can also be helpful.
The blacks are connecting stitches, they need to be stitched with a dense zigzag with under sewing, width 1.5mm, and density 7. A final BROTHER PE software file is also attached "V3 embroidery circuit.pes"
Attach a lycra fabric to the embroidery frame using the bulldog clips, make sure the fabric is in a high tension state. First the horizontal (straight) rows have to be stitched using the conductive thread. Then the isolation stitches have to come over the vertical rows, After which the vertical columns have to be stitched with conductive thread in the bobbin.
### Combine
Then the 3D print frame has to be attached to the embroidery frame, with the copper pads facing the conductive threads. After which the final stitches can be finsihed, connecting the two fabric sheets together. The fabric can be removed and the button matrix is finished.
Connecting the FabriClick
To interface the FabriClick, conductive coated copper wires can be crimped to the conductive yarns, make sure to first burn the isolation off. Then the copper wires can be interfaced with an Arduino, more detailed schematics in the pictorial.

## Have Fun!
We hope to have provided sufficient explanation and files to make it work for yourself, it might take some tweaking but when it is all set up and working it is rather easy to create samples! We hope to inspire you to continue and make cool things with the frame and don't hesitate to ask, we would love to help you explore the possibilities.

