# ExtractAnnotatedRegions
This pipeline will extract patches from the annotated regions from the WSI annotated by ASAP software based on the inputs such as patch size and resolution

Please follow these steps to extract patches - 

1. Install py-wsi package using => pip install py-wsi

   If you get error while installation, please check whether shapely is correctly installed. Follow this link - https://gis.stackexchange.com/questions/62925/shapely-not-installing-correctly and install py_wsi again.
   
   Even after, in case py_wsi is not getting installed (recommended : use it as a second option only) => clone the code from https://github.com/Srijay-lab/py-wsi and use the functions directly from the files in the folder - py_wsi/ . (you have to remove line "import py_wsi" from the code and place the main file accordingly so it can use functions from the dir py_wsi)
   
 
2. Clone the code from https://github.com/Srijay-lab/py-wsi. Go to the location where py-wsi is installed using pip, replace all the python files by the python files in py_wsi/ folder. This folder is contained in the folder you just cloned. 

3. From command line (after going to the folder containing main.py file of this repository), issue this command =>
    
   python main.py --wsi-folder [Folder where all WSI images are kept] --output-folder [Folder where you want to store annotated images] --patch-size [Patch Size] --magnification [Select the suitable magnification to set resolution, default is 10X] --labels [Give comma separated labels for annotations you want to be extracted, give each label as labelname:labelid, example - dcis:1,invasive:2,lcis:3]
   
4. The patches from annotated regions will start forming in the output folder you give. The format of the filename is as follows - 
   ([slide number] _ [x-coordinate of the mapped image to lower resolution] _ [y-coordinate] _ [annotation-label]).png. You can ignore the x and y coordinates as they are put in the name just to make image names unique.
   
Feel free to contact me anytime in case you get stuck in any step. Thank you.
