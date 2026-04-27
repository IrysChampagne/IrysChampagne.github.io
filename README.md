# IrysChampagne.github.io (the URL)

### This is probably supposed to be my official website or something 
### but rn it's a mother's day present

### Claude and I working on this together for one morning and, tbh,
### you can probably tell.

### Anyways, here is how to use this for your own madre:

### You will need:
### - hundreds of unique pictures (the more the better)
###    - any format is fine, script can deal with it
### - a way to run modaic_generator.py locally (I use VScode)
### - one specific picture to use at the portrait (mine= me_mom.png)
###     - this one has to be .png

### Here is a bit of code I put directly in my VS code terminal that transformed my .hei
### portrait image to .png; simply sub with your .heif if needed
### python -c "
### from pillow_heif import register_heif_opener
### register_heif_opener()
### from PIL import Image
### Image.open('me_mom.heic').save('me_mom.jpg', quality=90)
### "

### File organization for running:
### Create folder locally for this project, and put in:
###  - mosaic_generator.py
###  - the portrait picture of your choosing
###    - + .png version if not already in that format
###  - subfolder called "photos" that contain all the pics

### FIRST STEP - RUN THE .PY SCRIPT LOCALLY:
###  this will generate the mosaic.png
###  read the comments within the script to see what flags you
###  should use when you call the script, this was mineL
###  python mosaic_generator.py --portrait me_mom.heic --tiles ./photos/ --output mosaic.jpg
###  you might also need to do the couple pip installs it specifies at the top.
###  You can also play with the N col and N rows at the top depending on if your
###  portrait picture is in "landscape" orientation or not (mine was); if you don't,
###  it can "squish" the picture, but you can always adjust that.
###  This script will generate mosaic.png and also mosaic_manifest.json

### Once you have generated the mosaic:
### Create a free account on "Cloudinary":
###  - upload the mosaic.png to dashboard -> media library
###    - My original .png was too big so I had ChatGPT compress the image to <10MB
### Create new repo for this project on GitHub; follow "GitHub pages - Quickstart"
### (https://docs.github.com/en/pages/quickstart) you can stop before editting README.md;
### then add the following files onto the repo:
###  - index.html
###  - mosaic_manifest.json
###  - the portrait picture(s)

### If you have set-up your GitHub repo correctly per the "quickstart", you should be able
### to just go to the URL and see the interactive page(s) with all the pictures. 
### You should go into the HTML and change the titles, though, because mine are French
