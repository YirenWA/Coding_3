# Coding_3
## Project Content 
I aim to train a neural network model to depict the impact of plastic on the natural environment through image representation, creating a futuristic post-apocalyptic scene. This scene envisions a coexistence between plastic and organisms, all imagined by the machine.  
For this theme, I would like to collect the dataset myself. _CycleGAN_ is an unsupervised learning approach that can be trained on relatively small datasets and yield satisfactory results. Its adversarial learning mechanism enables image translation between two different domains while preserving the content and structure of the images.  
Therefore, I have chosen the domain transformation between artificial flowers (representing plastic) and real flowers. The adversarial training between the generator and discriminator can help the model capture the mapping relationship between these two domains.  

## Define the model  
### First Model: Discriminator  
I defined the discriminator. During the experimentation, I tried various loss functions such as Mean Squared Error, mean_absolute_error, and Binary Cross Entropy. Among them, I found that _"mean_absolute_error"_ yielded better results.
I utilized the _Adam_ optimizer and fine-tuned the parameters with a smaller learning rate after conducting multiple tests. Additionally, I emphasized the training of the generator, which led me to set the loss_weights to 0.46.  

![Discriminator](https://github.com/YirenWA/Coding_3/assets/119879041/ce3dfe4e-90de-41c4-b4b4-695a0a8ba40d)  

### Second Model: Generator  
I defined the generator, which is a composite model, that serves the purpose of training both the generator and discriminator.  

![Generator](https://github.com/YirenWA/Coding_3/assets/119879041/f14dae33-7290-4984-9cd6-520f8d1b59b8)

Finally, I proceeded with the training of the CycleGAN model.
