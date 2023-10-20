# Hackaton_Datasaur-2023

## The Task
There is a need to train a model to detect fake vehicle photos as people try to avoid technical inspection every year, using fake techniques such as photoshop and others.

In this task, according to the binary category, “0” refers to photos of vehicles, “1” are fictitious photos (taken from the monitor screen, Photoshop, etc.)

In “fictional” you can see that the photos themselves also grow on subclasses. They will all be designated "1" for this task.

## Dataset
The provided dataset consisted of 2 main folders. 

= The train set consist of 6585 images. A little over 4000 of them are real images, while the rest is fake.

= The test set has 777 images of vehicles. However, compared to the train set, the labels for them are unknown. We can obtain the accuracy value for it by submitting the prediction results to the Kaggle.

    .

    ├── train                    
    │   ├── real
    │   │   ├── image1.jpeg
    │   │   ├── image2.jpeg
    │   │   ├── ...
    │   ├── fake
    │   │   ├── image1.jpeg
    │   │   ├── image2.jpeg
    │   │   ├── ...
    
    ├── test              
    │   ├── image1.jpeg             
    │   ├── image2.jpeg            
    │   └── ...                 
     

### Data Augmentation
To increase the number of images for the training process, two versions of each images have been added into the mix, original and augmented. Both of them are rescaled to (224,224). For augmented images, they have been Horizontally Flipped, Brigtness Contrast Randomly changed, Randomly Rotated and Randomly Sligtly Blured.  

## Model

Several models have been tested to explore the possibilities. For optimizer "Adam" and for loss function "binary_crossentropy" were used. Also, to avoid overfitting, early stopping has been added monitoring validation loss.

## Results

Following tests with multiple CNNs, next table shows obtained results. With that, I ended up using EfficientNetB2.

Model |	Loss | Accuracy
--- | --- | -- |   
VGG16 |	0.851 |	0.9436
Xception |	1.268 |	0.8981
ResNet50 |	1.09 |	0.9356
EfficientNetB0 |	0.984 |	0.9289
EfficientNetB1 |	0.967 |	0.9493
EfficientNetB2 |	0.973 |	0.9579


In the end this project achieved 95.7% acc on public and 97.4% on private test sets, placing it 9th out of 45 teams.


