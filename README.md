# Transformers
This repo is a collection of resources and projects for the preparation of the [Machathon 3.0 competition](https://www.facebook.com/events/1004102850228797?ref=newsfeed).

### Online Courses
- [Structuring an ML Project Course](https://www.coursera.org/learn/machine-learning-projects?specialization=deep-learning#syllabus)
- [Transformers' tutorial](https://www.tensorflow.org/text/tutorials/transformer)
- [Tensorflow-Developer Specialization](https://www.coursera.org/professional-certificates/tensorflow-in-practice)
- [PYTORCH Toutrial](https://youtu.be/c36lUUr864M)



### Preparation Timeline

| 14/3 |                               |   
|------|-------------------------------|
| 15/3 | Tensorflow                    |
| 16/3 | Structuring ML                |
| 17/3 | PyTorch                       |
| 18/3 | HOLIDAY                       |
| 19/3 |                               |
| 20/3 | 2 NLP projects, Transformers. |



## Step1: Separate the white plane.
### Problems: 
- The line in the middle of the white plate may be misclassified.
- If we rotate the rotated white plate, thus the bounding box will be distorted
### Solutions:
- how much does this character fill the bounding box inside it
- take a threshold on the probability of the label its classified with.
- rotate the bounding box also
- We may consider dividing the plate to 2 parts, first part to then be classified as numbers, second part to be classified as alphabets
## Step2: Get countours on characters, filter countour by aspect ratio
### Problems: 
- Noisy countours, it may be a countour that represents no charcter.
- 1 Arabic Letter may consist of multiple charachters e.g ت this may consist of 2 countours.
### Solutions:
- Can consider merging 2 countours into 1, by doing a threshold between their distances.

## Step3: Give each extracted contour to the model, to be classified.
- Will consider training 3 model, 
-   one for classifing only arabic letter
-   one for classifying arabic alphabet
-   one for classifying both, in case separating the white plane to 2 parts didn't yeild got results.

