# K-Means-Segmentation-NOAA_Ice_Coverage

###  YOLOv11 Ice Coverage K-Means Segmentation Model
Understanding Arctic ice coverage is essential for understanding changing climate conditions and Arctic amplification. The Arctic Ocean occupies about 6 million square miles around Earth's North Pole, but this region has lost about 73,000 km^2 of ice per year since 1979. To better understand this changing landscape and ice loss, I have developed an unsupervised clustering model for high-performance image analysis and calculating ice coverage percentage. 
<br/>

To improve generalization, the data augmentation technique, Contrast Limited Adaptive Histogram Equalization (CLAHE), was applied. I also used HSV Conversion to transform images from the red, green, and blue (RGB) color space to a hue, saturation, and value (HSV) color value, which is easier for this image processing task. I used slic from the skimage library to generate superpixels which divides the image into meaningful regions, which makes subsequent analysis, like clustering, more effective. This model was trained at a resolution of 1024×1024 with a single batch of 480 images on Google Colab's GPU. No annotations were done on this dataset because they were not needed to complete this model's objectives.
<br/>

For more background on K-Means segmentation, its use cases, and the code and image processing behind this model, please visit https://oceancv.org/book/ClusterSegmentation_Kmeans.html# created by Katie Bigham and Atticus Carter for the University of Washington's OCEAN 462C course Computer Vision Across the Marine Sciences. 

 <br/>


### Ice Coverage Percentage
This model works best for distinguishing color segmentation and aerial percent coverage of ice. This unsupervised framework can detect the color contrast between deep blues and whites successfully. This K-means segmentation model is beneficial in workflows that incorporate manual review (e.g., imaging surveys) to confirm the results.
<br/>
 <br/>


### Model Details
Architecture: This streamlit interface https://github.com/AI-Ecology-Lab/K-Means-Segmentation  
Clustering: nC = 3

3 clusters best cover the differential colors between ice, ice/water mix, and water.

<br/>

### Dataset and Preprocessing
#### Source Imagery:
  Original resolution: 6048 × 4032\
  Total source images: 480 to cover 10 meter increments of the transect\
  Resolution range: ~12.21 MP to ~24.39 MP\
  Condensed resolution: 1024 × 1024

  This imagery was sourced from the 2019 Aerial Survey of Ice Seals in the Bering and Chukchi Sea sourced from NOAA Fisheries but was analyzed specifically for ice coverage, and did not utilize the annotated dataset.  

#### Processing:

This streamlit interface was used to process these images, with 3 clusters selected. \
  https://github.com/AI-Ecology-Lab/K-Means-Segmentation  

__sklearn.cluster (KMeans):__ A machine learning tool for clustering data, useful in tasks like color quantization or image segmentation.

__skimage.segmentation (slic):__ A function for segmenting images using a superpixel approach, useful for simplifying image data for analysis.

__skimage.util (img_as_float):__ Converts image data to floating-point representation, often needed for processing images in scientific computations.

<br/>
<br/>


### Example Clustered images
<img width="886" alt="Screenshot 2025-03-06 at 1 13 38 PM" src="https://github.com/user-attachments/assets/fa123215-01f6-4d64-9b36-66f76b305855" />
<br/>

### Results Analysis
<img width="1150" alt="Screenshot 2025-03-08 at 1 08 05 PM" src="https://github.com/user-attachments/assets/ac0f897e-90ff-456a-85f3-6f711b763519" />


Cluster 0 is white ice sheet

Cluster 1 is blue water cover

Cluster 2 is ice/water mix



<img width="1148" alt="Screenshot 2025-03-08 at 1 08 18 PM" src="https://github.com/user-attachments/assets/96e83a41-e88e-42cf-9cb9-1d9ca3aabd05" />

In this image, cluster 0 and 2 have been combined into the "ice" cover while cluster 1 has remained as "Water." This classification allowed for linear regression analysis of ice and water percent cover. 

<br/>

<img width="443" alt="Screenshot 2025-03-06 at 8 31 58 PM" src="https://github.com/user-attachments/assets/876626e4-7a31-4db9-922a-31a41cf39880" />

<br/>
 <br/>

### Disclaimer
This repository is a scientific product and is not official communication of the National Oceanic and Atmospheric Administration, or the United States Department of Commerce. All NOAA project content is provided on an ‘as is’ basis and the user assumes responsibility for its use. Any claims against the Department of Commerce or Department of Commerce bureaus stemming from the use of this project will be governed by all applicable Federal law. Any reference to specific commercial products, processes, or services by service mark, trademark, manufacturer, or otherwise, does not constitute or imply their endorsement, recommendation or favoring by the Department of Commerce. The Department of Commerce seal and logo, or the seal and logo of a DOC bureau, shall not be used in any manner to imply endorsement of any commercial product or activity by DOC or the United States Government.
