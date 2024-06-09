## ML4CV Project

The goal of this study was to implement and compare existing GAN architectures and methods to generate new images based on the CelebA-HQ dataset.

The architectures that were taken into consideration were five: DCGAN, LSGAN, SNGAN, WGAN-GP and EBGAN.

Two variations of WGAN were used, one with the discriminator using InstanceNorm2D and one without any normalization.

The methods were trained separately on the CelebA-HQ dataset and the comparison was done using their training losses and real/fake scores, then the generated samples of each model were compared to the true images to calculate the FID score.

### Conclusions

We can conclude this study by saying that we have 3 models (DCGAN, SNGAN and EBGAN) where the Discriminator overfit, in order to counter this problem we may apply some regularization techniques to the discriminator such as label smoothing or droupouts. 

It would be interesting to see if adding a Gaussian noise only to the input tensor of the discriminator would help to solve this problem or not. 

For the LSGAN one way to solve the problem might be using a gradient penalty. 

Due to lack of time and lack of GPUs these solutions weren’t implemented.

In the case of WGAN-GP without normalization, we don’t observe an improvement in the generated images across epochs, this might indicate that removing normalization could be impairing the network’s learning process.

It would be interesting to investigate the application of Spectral Normalization in the discriminator of both WGAN variants to assess its impact on training stability and generated image quality.
