# K-Means-Segmentation-NOAA_Ice_Coverage

###  YOLOv11 Ice Coverage K-Means Segmentation Model
Accurate understanding of Arctic ice coverage is essential for understanding changing climate conditions and Arctic amplification. The Arctic Ocean occupies about 6 million square miles around Earth's North Pole but this region has lost about 73,000 km^2 of ice per year since 1979. To better understand this changing landscape and ice loss, I have developed an unsupervised clustering model utilizing _________  for high-performance image analysis and calculating ice coverage percentage. 
<br/>

To improve generalization, the data augmentation technique CLAHE, was applied. The model was trained at a resolution of 1024×1024 with a single batch of 480 images on Google Colab's GPU. No annotations were done on this dataset because they were not needed to complete this model's objectives.
<br/>

 <br/>


### Ice Coverage Percentage
This model works best for distinguishing color segmentation and aerial percent coverage of ice. This unsupervised framework can detect the color contrast between deep blues and whites successfully. This K-means segmentation model is beneficial in workflows that incorporate manual review (e.g., imaging surveys) to confirm the results.
<br/>
 <br/>


### Model Details
Architecture: YOLOv11n\
Clustering: nC = 3

3 clusters best cover the differential colors between ice, ice/water mix, and water.

<br/>

### Dataset and Preprocessing
#### Source Imagery:
  Original resolution: 6048 × 4032\
  Total source images: 480 to cover 10 meter increments of the transect\
  Resolution range: ~12.21 MP to ~24.39 MP\
  Condensed resolution: 1024 × 1024\

<br/>
<br/>


### Example Clustered images
<img width="886" alt="Screenshot 2025-03-06 at 1 13 38 PM" src="https://github.com/user-attachments/assets/fa123215-01f6-4d64-9b36-66f76b305855" />
<br/>

### Results Analysis
<img width="1150" alt="Screenshot 2025-03-08 at 1 08 05 PM" src="https://github.com/user-attachments/assets/ac0f897e-90ff-456a-85f3-6f711b763519" />

<br/>
Cluster 0 is white ice sheet
Cluster 1 is blue water cover
Cluster 2 is ice/water mix
<br/>

<img width="1148" alt="Screenshot 2025-03-08 at 1 08 18 PM" src="https://github.com/user-attachments/assets/96e83a41-e88e-42cf-9cb9-1d9ca3aabd05" />
<br/>
In this image, cluster 0 and 2 have been combined into the "ice" cover while cluster 1 has remained as "Water." This classification allowed for linear regression analysis of ice and water percent cover. 
<br/>

<img width="443" alt="Screenshot 2025-03-06 at 8 31 58 PM" src="https://github.com/user-attachments/assets/876626e4-7a31-4db9-922a-31a41cf39880" />

<br/>
 <br/>

### Disclaimer
This repository is a scientific product and is not official communication of the National Oceanic and Atmospheric Administration, or the United States Department of Commerce. All NOAA project content is provided on an ‘as is’ basis and the user assumes responsibility for its use. Any claims against the Department of Commerce or Department of Commerce bureaus stemming from the use of this project will be governed by all applicable Federal law. Any reference to specific commercial products, processes, or services by service mark, trademark, manufacturer, or otherwise, does not constitute or imply their endorsement, recommendation or favoring by the Department of Commerce. The Department of Commerce seal and logo, or the seal and logo of a DOC bureau, shall not be used in any manner to imply endorsement of any commercial product or activity by DOC or the United States Government.
