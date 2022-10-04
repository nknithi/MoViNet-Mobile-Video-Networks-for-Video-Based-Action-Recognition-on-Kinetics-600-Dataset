# MoViNet-Mobile-Video-Networks-for-Video-Based-Action-Recognition-on-Kinetics-600-Dataset

##	Project Summary 

Effective video recognition models are creating new possibilities for applications like mobile cameras, the Internet of Things, and self-driving cars where precise and effective on-device processing is crucial. Although deep video modeling has made significant strides, it is still challenging to find models that operate on mobile platforms and provide accurate action identification in videos. The following study focuses on video-based action recognition using a pre-trained model called MoViNet, a family of memory and computation-effective video networks that use streaming video for online inference.

## Reasons for Choosing this Approach

While 3D convolutional neural networks (CNNs) are effective at video recognition, they are challenging to use on mobile devices due to their high memory and processing requirements. Furthermore, they do not support online inference. Even the more recent X3D networks, which provide more efficiency, occasionally fall short. They either demand a lot of memory resources for large temporal windows, which are expensive, or small temporal windows, which are less accurate. As a result, there is a significant difference in the performance of efficient and accurate models for video action identification. Although 2D MobileNet CNNs are quick and can handle real-time streaming video, they are often noisy and unreliable. 

MoViNet proposes, a three-step process to increase computational effectiveness while significantly lowering the peak memory utilization of 3D CNNs. The model has demonstrated state-of-the-art accuracy and efficiency on several large-scale video action recognition datasets with these three essential steps. To create effective and diverse 3D CNN architectures, a video network search space is first designed, and neural architecture search is used. Second, the decoupling of memory from the duration of the video clip using the Stream Buffer approach enables 3D CNNs to include streaming video sequences of any length for both training and inference with a small constant memory footprint. Third, a straightforward ensembling strategy is suggested to further increase accuracy without reducing efficiency. These three progressive techniques allow MoViNets to achieve good accuracy and efficiency.

## Dataset Used

The model is trained on Kinetics 600, a collection of large-scale, high-quality datasets that, depending on the dataset version, can contain up to 650,000 URL links to videos that represent 400, 600, or 700 different human action classes. Both human-object interactions, such as playing instruments, and human-human interactions, such as shaking hands and, playing the trumpet, robot dancing, or bowling are seen in the videos. At least 400/600/700 videos are included in each activity class.

## Architecture

With MoViNets, users may make use of the advantages of 3D video classifiers and 2D frame-based classifiers while minimizing their drawbacks. Instead of 3D CNNs, causal convolutions are used in this hybrid technique. When modeling temporal data, a type of convolution called causal convolutions is employed to ensure that models don't deviate from the ordering specified by the developers. This allows users to cache intermediate activations across frames with a Stream Buffer. The method duplicates all 3D operations' input activations, an output from the model, and inputs them back into the model on the subsequent clip input. As a result, MoViNets can receive one frame input at a time. This reduces peak memory usage with no loss of accuracy. In 3D CNNs, given the model is processing all frames in a video clip simultaneously, it takes up significant memory.

Additionally, Neural Architecture Search (NAS), a widely utilized method for automating the design of artificial neural networks, is employed to look for effective model configurations. On video datasets throughout network width, depth, and resolution, it looks for model configurations. It develops a collection of action classifiers that produce predictions that move smoothly over time based on the frame content. This solves the issue of output predictions on 2D frames with sub-optimal performance due to the absence of temporal reasoning.

## Results and Conclusion

![image](https://user-images.githubusercontent.com/47960029/193860532-83c2afc9-8029-4184-9663-1430a5cfbc26.png)
![image](https://user-images.githubusercontent.com/47960029/193860870-0f9dae58-f6f7-4b6b-acb2-e2569de2ed94.png)

The above two images show the output or the results.

MoViNets provide a highly efficient set of models that are incredibly effective and easily adapt to various video recognition datasets. MoViNets drastically lower training and inference memory costs when used with stream buffers, and they also provide online inference on streaming video. Other related works also showed that the above-mentioned three progressive techniques allow MoViNets to achieve state-of-the-art accuracy and efficiency on the Kinetics, Moments in Time, and Charades video action recognition datasets. 
