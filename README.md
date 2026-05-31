# Generative Adversarial Network (GAN) – MNIST Digit Generation

A **Generative Adversarial Network (GAN)** implemented using **TensorFlow/Keras** to generate handwritten digit images similar to the MNIST dataset.  
This project includes the full training pipeline, Generator & Discriminator architectures, loss visualization, and sample outputs.

---

## 🚀 Project Overview

This project implements a Deep Convolutional GAN (DCGAN) trained on the **MNIST handwritten digits dataset**.

The GAN consists of:

- **Generator** → Creates synthetic digit images from random noise  
- **Discriminator** → Classifies images as real (MNIST) or fake (generated)  
- **Adversarial Training Loop** → Both networks improve by competing against each other  

Training is performed for **50 epochs**, with generated samples saved at each epoch.

---

## 🎯 Objectives

- Implement a GAN from scratch using TensorFlow/Keras  
- Train a Generator to produce realistic MNIST‑like digits  
- Visualize training progress using loss curves  
- Save generated images at each epoch  
- Analyze challenges such as instability and mode collapse  

---

## 🧠 How GANs Work

GANs involve two neural networks trained simultaneously:

### **Generator (G)**
- Input: 100‑dimensional random noise  
- Output: 28×28 grayscale image  
- Learns to map noise → realistic digits  
- Uses **Conv2DTranspose**, **BatchNorm**, **LeakyReLU**, **Tanh**

### **Discriminator (D)**
- Input: 28×28 image  
- Output: Real (1) or Fake (0)  
- Uses **Conv2D**, **LeakyReLU**, **Dropout**, **Dense**

The training objective:

- **G tries to fool D**  
- **D tries to correctly classify real vs fake**

---

## 🏗️ Model Architecture
### **Generator**
  Dense → BatchNorm → LeakyReLU
  Reshape to (7,7,256)
  Conv2DTranspose (128) → BN → LeakyReLU
  Conv2DTranspose (64) → BN → LeakyReLU
  Conv2DTranspose (1, activation='tanh')

### **Discriminator**
  Conv2D (64) → LeakyReLU → Dropout
  Conv2D (128) → LeakyReLU → Dropout
  Flatten → Dense(1)


---

## 🧪 Training Details

- **Dataset:** MNIST (60,000 images)  
- **Epochs:** 50  
- **Batch Size:** 256  
- **Optimizer:** Adam (lr=0.0002, β1=0.5)  
- **Loss:** Binary Crossentropy (from_logits=True)  
- **Checkpoints:** Saved every 15 epochs  

---

## 📌 Observations

- Generator improves significantly after ~20 epochs  
- Discriminator initially dominates, then stabilizes  
- Loss curves fluctuate (normal for GANs)  
- Final outputs resemble MNIST digits with good clarity  
- Fixed seed helps visualize progress consistently  

---

## ⚠️ Challenges Faced

- **Mode Collapse:** Generator sometimes produced similar digits  
- **Training Instability:** Sensitive to learning rate & batch size  
- **Discriminator Dominance:** Required careful balancing  
- **Slow Convergence:** GANs need many epochs for quality results  
- **Subjective Evaluation:** Visual inspection required  

---

## 🏁 Conclusion

This project successfully demonstrates the implementation and training of a GAN capable of generating realistic handwritten digits. Despite challenges like instability and mode collapse, the final results show strong generative performance and provide a solid foundation for further GAN experimentation.

---


---

## ⭐ Future Improvements

- Train for 100+ epochs  
- Use a deeper DCGAN architecture  
- Try Conditional GAN (cGAN)  
- Experiment with Fashion‑MNIST or CIFAR‑10  







### **Generator**

