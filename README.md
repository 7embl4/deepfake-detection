# Deepfakes Detection
Repository of course work. This research based on paper [*Recurrent Convolutional Strategies for Face Manipulation Detection in Videos, CVPR Workshop 2019*](https://arxiv.org/abs/1905.00582) (*).

## Model
Hierarchical model with several RNNs that learn features on different levels of image representation made by image encoder.
This is the same architecture used in (*), but I think this diagram looks better than the papers one.
![](https://github.com/7embl4/deepfake-detection/blob/main/architecture.drawio.png)

## Results 
Unlike (*) I used two models based on transformer architecrure: ViT and SwinTransformer. And also tried non-hierarchical method, using only final representations of Image Encoders. You can see the result of the research in table below. 
As you can see, transformers have good accuracy (especially Swin), but there are still the gap to CNN model. However I used FaceForensics++ dataset, that actually quite small. 
Since transformer architecture perform as better as more data used for training, there is a chance that transformers may show better results on large datasets in comparison to CNNs. 
Also I can say, that accuracy highly depends on network architecture and hyperparameters on training (based on my expirience on this work), I've tested some variants to maintain training stability and good results, but it may not be the better scenario.
So there is a room for experiments.

| Model                | Deepfakes | Face2Face | FaceSwap |
| -------------------- | :-------: | :-------: | :------: |
| Single RNN (ViT)     |   90.0    |   78.5    |   74.5   |
| ViT                  |   89.5    |   82.5    |   84.0   |
| SwinTransformer      |   92.5    |   88.5    |   90.0   |
| ResNet-50 (baseline) |   94.6    |   90.25   |   90.95  |
