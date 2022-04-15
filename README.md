# Transformers
## Arabic licence plate recognition :car:
- Solution to the kaggle competition [Machathon 3.0](https://www.kaggle.com/competitions/machathon-3/overview).
- Ranked in the top :six: at the final evaluation phase.
- Check our solution now on [collab](https://colab.research.google.com/drive/15LM0YL0Yi3KdwhPBrGH_G3iGkx6eT5XZ?usp=sharing)!

## Preprocessing Pipeline
![The schematic of the processor](images/preproccessing_pipeline.png)

### Step1: Separate the white plane.
### Problems: 
- The line in the middle of the white plate may be misclassified.
- If we rotate the rotated white plate, thus the bounding box will be distorted
### Solutions:
- how much does this character fill the bounding box inside it
- take a threshold on the probability of the label its classified with.
- rotate the bounding box also
- We may consider dividing the plate to 2 parts, first part to then be classified as numbers, second part to be classified as alphabets
### Step2: Get countours on characters, filter countour by aspect ratio
### Problems: 
- Noisy countours, it may be a countour that represents no charcter.
- 1 Arabic Letter may consist of multiple charachters e.g ت this may consist of 2 countours.
### Solutions:
- Can consider merging 2 countours into 1, by doing a threshold between their distances.

### Step3: Give each extracted contour to the model, to be classified.
- Will consider training 3 model, 
-   one for classifing only arabic letter
-   one for classifying arabic alphabet
-   one for classifying both, in case separating the white plane to 2 parts didn't yeild got results.

## Files Hirarchy
### Scripts
- extract_bbx_xml.ipynb 
  - Takes directory of images and their bbx data stored in an xml files, and crop the bbxs from the images.
  - The xml file contains licence label(name), xmin, ymin, xmax, ymax of the bbxs in an image.
- extract_bbx_txt.ipynb 
  - Takes directory of images and their bbx data stored in a txt files, and crop the bbxs from the images.
  - The txt file corresponding to one image may consist of multiple bbxs, each corresponds to a row of xmin,ymin,xmax,ymax for that bbx.
- crop_right_noise
  - Crops an image with some percentage and replace with the cropped image.
- model.ipynb
  - The preprocessing and modelling stage

## Contributors
### This masterpiece was designed, and implemented by
<table align="center">
  <tr>
    <td align="center">
    <a href="https://github.com/hoskillua" target="_black">
    <img src="https://avatars.githubusercontent.com/u/47090776?v=4" width="100px;" alt="Hossam"/>
    <br />
    <sub><b>Hossam Saeed</b></sub></a>
    </td>
    <td align="center">
    <a href="https://github.com/Mostafa-wael" target="_black">
    <img src="https://avatars.githubusercontent.com/u/56788883?v=4" width="100px;" alt="Mostafa wael"/>
    <br />
    <sub><b>Mostafa Wael</b></sub></a>
    </td>
    <td align="center">
    <a href="https://github.com/NadaElmasry" target="_black">
    <img src="https://avatars.githubusercontent.com/u/57152677?v=4" width="100px;" alt="Nada Elmasry"/>
    <br />
    <sub><b>Nada Elmasry</b></sub></a>
    </td>
    <td align="center">
    <a href="https://github.com/NouranHany" target="_black">
    <img src="https://avatars.githubusercontent.com/u/59095993?v=4" width="100px;" alt="Noran Hany"/>
    <br />
    <sub><b>Noran Hany</b></sub></a>
    </td>
  </tr>
 </table>
