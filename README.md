# PCB christmas-card
PCB christmas card designed in kicad 7. 
Uses CMOS 555 chips to flash LED's.

You can get a 4 tone image on your pcb at no additional cost. I have included a photoshop file where you can use thresholds to adjust the look. 
From light to dark, the four tones avaliable are: 
	* Silkscreen; 
	* copper without soldermask (Silver if you order HASL, gold with ENIG); 
	* copper with solder mask (whatever color you choose); 
	* soldermask with no copper
Steps
* Input your image in the three folders 
* Adjust thresholds
* Turn of the color-layers visibility, and make only one layer visible at the time
* Export these 3 resulting black/white 1-bit images
* use the kicad image conversion tool to with your images.
* The tool has options to make the silkscreen and soldermask hole. For the copper layer, export a silkscreen, then open the textfile and search and replace F.SilkS with F.Cu
Some manufacturers remove silkscreen wherever you have exposed copper (i think JLC does this for example). To rectify this, make shure to subtract your "silkscreen" image from your "copper without soldermask"/"soldermask hole" image

In kicad, if you have the copper image imported, the build-zones function completely crashes the program. Make sure to complete your circuit and zones before you import it. Take note that the DesignRulesChecker and the fabrication outputs functions will try to rebuild zones by default (again crashing the program) so make sure to run DRC before you import the image, and uncheck the "build zones" from the fabrication output

# Circuit diagram
![image](https://github.com/user-attachments/assets/5aa14d33-abe8-495e-84ce-b962c759239a)
