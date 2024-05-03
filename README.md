# Enhancing X-ray Images to Resemble MRI or CT Scans
Medical imaging plays a crucial role in diagnosing and monitoring various health conditions. X-ray imaging is one of the most widely used modalities due to its accessibility and ability to provide valuable insights into skeletal structures and certain soft tissues. However, compared to more advanced modalities like MRI (Magnetic Resonance Imaging) and CT (Computed Tomography) scans, X-ray images often lack the clarity and detail necessary for accurate diagnosis, particularly in the visualization of soft tissues and organs.
In this project, we aim to bridge the gap between X-ray imaging and MRI/CT scan imaging by enhancing X-ray images to resemble MRI or CT scan-like images using image enhancement techniques. By improving the quality and visibility of structures in X-ray images, we hope to provide medical professionals with enhanced diagnostic tools that can aid in more accurate and reliable diagnoses.


## How does CycleGAN work
Adversarial training lies at the core of CycleGAN, involving two main components: the generator and the discriminator. The generator aims to learn the mapping from one domain to another, such as transforming X-ray images into MRI or CT scan images, while the discriminator works to distinguish between translated images and real images from the target domain. This dynamic sets up a competitive learning process where the generator strives to produce realistic images that can fool the discriminator, while the discriminator becomes adept at discerning real from fake images.

A crucial aspect of CycleGAN is its cycle consistency mechanism, which enables bidirectional translation between domains. This means not only learning mappings from X to Y but also from Y to X. To ensure consistency in both directions, a cycle consistency loss is imposed, which enforces the idea that translating an image from X to Y and then back to X should result in an image similar to the original input X. This loss function plays a vital role in guiding the generators (G and F) to learn mappings that are inverses of each other.

During training, both generators and discriminators are trained simultaneously. The generators aim to minimize a combined loss, consisting of both adversarial loss (which encourages realistic translation) and cycle consistency loss (which enforces consistency in both directions). On the other hand, the discriminators aim to maximize this combined loss, effectively distinguishing real from fake images while also penalizing inconsistencies in the translations.

In practice, during inference, input images from the source domain are fed into the appropriate generator, whether it's translating X-ray images to MRI scans or vice versa. The result is a set of translated images in the target domain, opening up possibilities for various applications in medical imaging, artistic style transfer, and more.
![image](https://github.com/vihan17/GANsproject/assets/91966446/fec55559-272f-465c-ac1b-c7daea754117)


## Work Flow

Data Collection: Start by collecting a diverse dataset comprising X-ray images, MRI scans, and CT scans from medical databases and institutions. Ensure the dataset encompasses a wide range of anatomical regions and medical conditions to capture real-world variability.

Data Preprocessing: Standardize the dataset by normalizing pixel values, resizing images, and performing data augmentation techniques like rotation and flipping to enhance dataset diversity and uniformity.

Image Enhancement Techniques:Experiment with various enhancement methods such as histogram equalization, adaptive histogram equalization, denoising algorithms, and edge enhancement techniques. Explore combinations of these techniques to optimize image quality and clarity.

Deep Learning Approach: Investigate the use of deep learning models like GANs, cGANs, and CNNs to learn the mapping between X-ray images and MRI/CT scan-like images. Train the models on the preprocessed dataset using suitable loss functions and optimization techniques.

![image](https://github.com/vihan17/GANsproject/assets/91966446/0d2cf8da-777e-428c-837f-4b6561c34313)




## Getting Started

### Prerequisites
- Linux, macOS or Windows
- Python 3 (tested version 3.6)
- CPU or NVIDIA GPU + CUDA CuDNN

### Installation
- Clone this repository
- Setup Python environment (preferably version 3.6) with **pip** command available for this project
- Check _requirements.txt_ with the list of all dependencies. Select appropriate Tensorflow dependency given your configuration.
- Install all dependencies by executing: `pip install -r requirements.txt` into the Python environment.

### Train/test CycleGAN with one of the provided examples
- Start a **Jupyter server** within your Python environment by executing a command: `jupyter notebook`. Make sure that this command is executed relative to the project directory, so the project's script can be imported with no changes to the code.
- Check the log of a Jupyter server in the console. There should be a server's address. Use it to interact with the server.
- Open notebook on the server and run all cells. The example should run as it is (it will automatically download the data set for you)

### Sample XRay images
![image](https://github.com/vihan17/GANsproject/assets/91966446/fd82d0f1-3b4d-4c3b-b2ee-044acf71b033)


### Results After Image Enhancement
Histogram Equalisation
![image](https://github.com/vihan17/GANsproject/assets/91966446/5ed5c9c7-914b-44a5-859c-cc2aa13d958c)

Adaptive Histogram Equalisation
![image](https://github.com/vihan17/GANsproject/assets/91966446/bce75a91-df13-4635-8b94-be75b7d0063e)

### Final Results
![image](https://github.com/vihan17/GANsproject/assets/91966446/2395f1a2-3685-4cf7-bee6-8a72b9441d90)


## Resources

## Dataset
https://www.shaip.com/offerings/x-ray-images-datasets/
https://www.kaggle.com/datasets/paultimothymooney/chest-xray-pneumonia

### References
- https://medium.com/analytics-vidhya/transforming-the-world-into-paintings-with-cyclegan-6748c0b85632
- https://machinelearningmastery.com/how-to-develop-cyclegan-models-from-scratch-with-keras/
- https://medium.com/datadriveninvestor/style-transferring-of-image-using-cyclegan-3cc7aff4fe61
- https://www.tensorflow.org/tutorials/generative/cyclegan
- https://arxiv.org/pdf/1703.10593.pdf
- https://towardsdatascience.com/style-transfer-with-gans-on-hd-images-88e8efcf3716

