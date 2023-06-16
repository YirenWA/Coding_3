# Coding_3
## Project Content 
_Video Link_: https://youtu.be/9Pqtwk2Tl1M  

I aim to train a neural network model to depict the impact of plastic on the natural environment through image representation, creating a futuristic post-apocalyptic scene. This scene envisions a coexistence between plastic and organisms, all imagined by the machine.  
For this theme, I would like to collect the dataset myself. _CycleGAN_ is an unsupervised learning approach that can be trained on relatively small datasets and yield satisfactory results. Its adversarial learning mechanism enables image translation between two different domains while preserving the content and structure of the images.  
Therefore, I have chosen the domain transformation between artificial flowers (representing plastic) and real flowers. The adversarial training between the generator and discriminator can help the model capture the mapping relationship between these two domains.  

![封面-01](https://github.com/YirenWA/Coding_3/assets/119879041/e37bcbe0-23de-48e2-9d43-241c36f96fed)

## Define the model  
### First Model: Discriminator  
I defined the discriminator. During the experimentation, I tried various loss functions such as Mean Squared Error, mean_absolute_error, and Binary Cross Entropy. Among them, I found that _"mean_absolute_error"_ yielded better results.
I utilized the _Adam_ optimizer and fine-tuned the parameters with a smaller learning rate after conducting multiple tests. Additionally, I emphasized the training of the generator, which led me to set the loss_weights to 0.46.  

![Discriminator](https://github.com/YirenWA/Coding_3/assets/119879041/ce3dfe4e-90de-41c4-b4b4-695a0a8ba40d)  

### Second Model: Generator  
I defined the generator, which is a composite model, that serves the purpose of training both the generator and discriminator.  

![Generator](https://github.com/YirenWA/Coding_3/assets/119879041/f14dae33-7290-4984-9cd6-520f8d1b59b8)  

Finally, I proceeded with the training of the CycleGAN model.  

## Training dataset
In the data training phase, I collected two datasets, one with 400 images and the other with 410 images. When loading the image dataset, I resized the images to (256, 256) to ensure a consistent size.  
After several tests, adjustments were made to the image dataset. The images in the dataset needed to have flowers positioned in reasonable locations, while the plastic flower images needed to avoid an excessive proportion of pure black areas in the frame.  

![process-01](https://github.com/YirenWA/Coding_3/assets/119879041/01dbcd1b-ddbc-4125-8241-c49d99797226)  

Finally, I selected _50 samples_ for training. One epoch consists of 500 iterations, and after multiple tests, the training was conducted with epoch=90.   
During the training process, I discovered that the generated images better expressed my theme. Therefore, I also added storage for the generated images in the model. The key idea of CycleGAN is to introduce cycle consistency loss, which involves converting the transformed images back to the original domain.  

![Generated output folder](https://github.com/YirenWA/Coding_3/assets/119879041/3a650888-7f45-4aa6-9dc3-2d3247b75601)

## Presentation of results
The images have a contaminated light sensation.  
![results-01](https://github.com/YirenWA/Coding_3/assets/119879041/31f68695-ab1e-43de-a873-0f1962dccdab)  

## Other
Initially I also tried this model many times with different datasets.  

![other-01](https://github.com/YirenWA/Coding_3/assets/119879041/83455c3d-9b31-417c-9559-626b6a617c84)

