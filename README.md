# Physics-Informed-Neural-Networks_Autism

### **Overall Architecture & Steps**  

1️⃣ **Load & Preprocess Image Data**  
   - Load MRI images from a directory.  
   - Resize images to **128×128 pixels**.  
   - Split data into **training (80%)** and **validation (20%)** sets.  
   - Normalize pixel values to **[0, 1]**.  

2️⃣ **Define CNN Model**  
   - **Input:** 128×128 RGB images.  
   - **Feature Extraction:**  
     - Convolutional layers with ReLU activation.  
     - Max pooling layers to reduce dimensionality.  
   - **Classification:**  
     - Flattening layer → Fully connected layer.  
     - Output layer with **sigmoid activation** (binary classification).  

3️⃣ **Define Physics-Informed Loss (PINN)**  
   - Standard **Binary Cross-Entropy Loss**.  
   - **Brain Symmetry Constraint** → Penalizes asymmetry.  
   - **Regularization Term** → Prevents overconfident predictions.  
   - **Total Loss = Classification Loss + Symmetry Loss + Regularization**.  

4️⃣ **Train Model with PINN Loss**  
   - Use **Adam optimizer**.  
   - Train for **10 epochs**.  

5️⃣ **Evaluate Model**  
   - Compute **loss & accuracy** on validation data.  
   - Print final **test accuracy**.  
