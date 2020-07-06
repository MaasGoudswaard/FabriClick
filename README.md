# FabriClick: Interweaving Pushbuttons into Fabric Using 3D Printing and Digital Embroidery
Presenting a new way to seamlessly integrate tactile pushbuttons into fabrics to enable eyes-free inputs on soft wearables!  
This is the repository from the DIS2020 Pictorial. Here, you can find the files to fabricate your own FabriClick (with detailed instructions below!)

Pictorial: https://doi.org/10.1145/3357236.3395569

You can also watch the video: https://www.youtube.com/watch?v=m9yXMVoc-N0&feature=youtu.be

![alt text](https://github.com/MaasGoudswaard/FabriClick/blob/master/FabriClick.JPG?raw=true)

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
1. Prepare the parts by laser cutting the “Frame design V3 drawing.DXF” design from 8mm thick acrylic.
2. Assemble the cut pieces as illustrated in the pictorial, and the figure below. The baseplate can be screwed together using M4 bolts.
3. Remove the frame connectors from the 180mm x 130mm embroidery frame, and attach them to the laser cut embroidery frame using M3 bolts. You may need to slightly drill out the holes to achieve a tight fit.

![alt text](https://github.com/MaasGoudswaard/FabriClick/blob/master/FrameSystem.png?raw=true)

## Calibration
### Embroidery Machine
1. After assembling the frame, take the embroidery frame and slot it into your digital embroidery machine. Make sure the bolts are tightly fastened, preventing any further movement during embroidery.
2. Open the “Calibration square embroidery.ai” file and export it as a WMF format file. Open the file on the digital embroidery machine, and make sure that the pattern is auto-centred on the machine’s workspace. Tightly stretch the lycra sheet onto the laser cut embroidery frame using bulldog clips, ensuring that the fabric is in a high-tension state
3. Embroider the calibration square pattern onto the lycra fabric using a non-conductive yarn

### 3D printer
1. Once the embroidery pattern is prepared, move to the 3D printer. Using large bulldog clips, attach the baseplate onto the 3D printer’s print bed.
2. Align the embroidery frame within the laser cut 3D print frame, and place the two frames into the baseplate with the connectors facing down. Ensure both frames fit tightly by adjusting the 4 corners.
3. Turn on the 3D printer and calibrate the Z-axis, adjusting the positioning to line up with the embroidered cross. You will be trying to print directly onto this pattern. We recommend creating a new custom printer profile using your slicer program to make this process easier, using a larger 140mm x 190 mm build-plate surface to ensure that you do not hit the embroidery frame.
4. Upload the “Calibration square printer.STL” file to the 3D printer and begin your print.
5. As the print proceeds, use it as a guide to adjust the positioning of the baseplate to align your two (embroidery AND 3D printing) workspaces. Adjust the offsets of the printhead in the slicer until you reach the right, accurate alignment. You may also adjust the baseplate to achieve alignment, but we recommend doing as much of this as you can digitally for best practice.
6. Once the 3D printed cross lines up directly over the embroidered square pattern, you have successfully calibrated the baseplate!

![alt text](https://github.com/MaasGoudswaard/FabriClick/blob/master/Calibration.jpg?raw=true)

## Fabricating the buttons
Once the baseplate is properly installed, you can begin making your FabriClick!
### 3D print the button structure layer
1. Begin by tightly stretching a lycra fabric onto the laser cut 3D print frame using bulldog clips, making sure to have as much tension as possible in the fabric while maintaining an even stretch.
2. Align and snap the 3D printing frame into the baseplate, with the fabric side facing up.
3. Upload the “V3 3D print button.STL” file onto the 3D printer, and begin printing directly onto the lycra fabric. Ensure that your 3D printer Z-axis is calibrated correctly to ensure that you are printing INTO the fabric layer instead of loosely on top. This is important to achieve sufficient print adhesion on the fabric
4. Once printed, remove the frame and attach the copper pads to the fabric layer, positioning one pad underneath the centre of each 3D printed button. The copper pads should not be wider than the circular button touchpoints.

### Embroider the sensing layer
1. Open the “V3 embroidery matrix.ai” file and export it as a WMF format file. Open the file on the digital embroidery machine, and make sure that the pattern is auto-centred on the machine’s workspace.
2. This pattern requires specific different stitches to be sewed in a specific order, so carefully prepare the appropriate stitch settings for each colour. Settings may differ between each thread, machine and fabric:
  - Red lines: These stitches are conductive tracks, so the conductive yard needs to be placed onto the bobbin. These tracks need to be stitched with a 1.5mm wide zigzag stitch with a density of 1 stitch per mm (or preferably even lower) WITHOUT undersewing. In the areas where the rows and columns jump over one another (where the green stitches are located), the zigzag stitches need to be manually simplified to create one long stitch across the isolation stitch. This creates perpendicular stitching between the track and the isolation, reducing the chances of track stitches permeating the isolation stitch and creating a short circuit.
  - Green stitches: These are isolation stitches. They need to be stitched with a very dense stem and a large angle. This will require some experimentation as the denser the stitch is, the better the track isolation will be. You can also use a thicker yarn in the bobbin to improve this stitch.
  - Black stitches: These are connecting stitches.  They need to be stitched using a dense zigzag, with 1.5mm width and 7 density, and undersewing.
  - You can refer to the “V3 embroidery circuit.pes” file (compatible with BROTHER PE software) for additional reference.
3. Once the coloured stitches have been assigned their appropriate settings, tightly stretch a lycra fabric onto the laser cut embroidery frame using bulldog clips. Aim to have as much tension as possible in the fabric while maintaining an even stretch.
4. Begin embroidering the patterns by colour, following this precise order:
  - First, stitch the HORIZONTAL RED rows using the conductive thread in the bobbin.
  - Next, stitch the GREEN ISOLATION stitches using a non-conductive thread. They need to be stitched the horizontal red rows.
  - Finally, stitch the RED VERTICAL columns. Don’t forget to switch the conductive thread back into the bobbin!
5. Do not turn off or cancel this current embroidery pattern! We will be coming back to it in a moment.

![alt text](https://github.com/MaasGoudswaard/FabriClick/blob/master/MatrixCircuitry.png?raw=true)

### Combine the button and sensing layers
1. Gently remove the embroidery frame from the digital embroidery machine.
2. Attach the 3D print frame with the lycra fabric onto the laser cut embroidery frame, aligning them together to create a snug fit. The copper pads on the 3D printed layer should be directly facing the exposed conductive threads.
3. Insert the combined frames into the digital embroidery machine, ensuring that you maintain the original/previous embroidery frame orientation. This will ensure that you retain your relative stitching position.
4. Begin the final embroidery, stitching the BLACK CONNECTOR stitches which will connect and combine the two (3D printed and embroidered) fabric sheets together.
5. Once the connectors are completely embroidered, remove the frames from the digital embroidery machine. You can now remove the finished button matrix!

### Connecting the FabriClick
1. Finally, we need to connect the FabriClick to a processor to begin using it! To interface the FabriClick, carefully follow the horizontal row and vertical column stitches to their loosened end points. Once loose, attach these tracks to conductive coated copper wires using small crimps. Make sure to burn the ends of the copper wires to remove their insulation coating, or they won’t connect!
2. Once the copper wires are connected, these tracks can be wired to a processor using the same wiring principles as any standard button matrix. You can attach connectors to the copper wires for easier plug-and-play wiring, or solder them directly. For more details on wiring examples, check out the detailed schematic provided in the pictorial!

![alt text](https://github.com/MaasGoudswaard/FabriClick/blob/master/ConnectingFabriClick.JPG?raw=true)

## Have Fun!
By now, we hope you would have had the sufficient explanation and files to make your own FabriClick. It might take some tweaking and experimenting at first, but that’s just part of the fun. We hope you will be inspired to experiment, explore, and continue to make cool new things with our designs and frames! Finally, if you have any questions, please don’t hesitate to ask! Email us, and we would love to help (email us at: m.p.goudswaard@student.tue.nl and abela@sfu.ca)


