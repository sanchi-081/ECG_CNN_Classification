**ECG CNN Classification: Optimized Deep Learning for Wearable Devices**

🚀**Overview**

This project implements and evaluates four 2D Convolutional Neural Network (CNN) architectures—AlexNet and three ResNet variants (11, 20, and 29 layers)—for the multiclass classification of ECG images. The core objective is to identify four clinically relevant cardiac conditions with high accuracy and efficiency suitable for integration into wearable biomedical devices.

This repository demonstrates a complete deep learning workflow, from robust image processing and comparative model training to optimized edge deployment on the NVIDIA Jetson Nano

💾 **Dataset**

This study utilizes a 12-lead publicly available ECG image dataset sourced from (https://data.mendeley.com/datasets/gwbz3fsgp8/2).

**Data Description**

- Source: A. H. Khan and M. Hussain, “ECG Images dataset of Cardiac Patients,” Mendeley Data, V2, 2021, doi: 10.17632/gwbz3fsgp8.2.

- Total Images: 928 ECG images.

- Input Format: Images resized to 224×224×3 pixels.

- Classes: The dataset is categorized into four clinically relevant classes:

           1)Normal Heartbeat

           2)Abnormal Heartbeat (Abnormal Heartbeat)

           3)Myocardial Infarction (MI)

           4)History of MI (PMI)

- Data Balancing: The minority class, History of MI, was oversampled to address class imbalance and ensure robust model generalization across all four categories.

<img width="638" height="538" alt="Screenshot 2025-09-29 225921" src="https://github.com/user-attachments/assets/e4aca592-6fdb-44d6-8c4e-1937bfaed0c9" />

**Classification Class Examples** 

Below are visual examples of the four primary categories used for classification.  

| Category                   | Description                                                                      |
|----------------------------|----------------------------------------------------------------------------------|
| Normal Heartbeat           | Represents a healthy, rhythmic heart pattern.                                    |
| Abnormal Heartbeat(HB)     | ECGs showing deviations from the normal sinus rhythm.                            |
| Myocardial Infarction (MI) | Images indicating an acute heart attack (ST-segment elevation/depression).       |
| History of MI (PMI)        | Images showing signs of a past myocardial infarction.                            |

**Training and Analysis Workflow**

The primary analyses and model training were conducted using the Jupyter Notebooks located in the ./notebooks directory:

**📊Model Comparison and Results**

This study conducted a rigorous comparative analysis across AlexNet and three ResNet variants (11, 20, and 29 layers) trained over 25, 50, and 75 epochs.

| Model         | Peak Accuracy            | Peak F1-Score     | Key Insight                                                                                          |
|---------------|--------------------------|-------------------|------------------------------------------------------------------------------------------------------|
| **AlexNet**   | 90.2% (at 75 epochs)     | 0.91              | Served as a reliable baseline with steady, but lower, performance gains across epochs.               |
| **ResNet-11** | 96.9% (at 75 epochs)     | 0.97              | Demonstrated the best balance of performance, stability, and resistance to overfitting.              |
| **ResNet-20** | 95.8% (at 75 epochs)     | 0.96              | Consistent performance, but showed less stability and greater training loss than ResNet-11.          |
| **ResNet-29** | 90.4% (at 75 epochs)     | 0.91              | Exhibited instability, showing that increased depth did not improve generalization for this dataset. |

Full loss/accuracy curves, F1-Score comparisons, and detailed confusion matrices are available in the ./results directory:


**🔌Edge Deployment**

To validate the model's suitability for real-time, low-power applications like wearable diagnostic devices, the top-performing ResNet-11 model was optimized and deployed on the NVIDIA Jetson Nano.
This optimization utilized INT8 quantization via TensorFlow Lite (TFLite) to significantly reduce the model's footprint and accelerate inference speed without compromising accuracy.

The full details on the quantization process, resource usage, and comprehensive deployment results can be found in a table here: ./deployment/jetson_nano_results.md
