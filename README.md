# DMF
Ground filtering algorithms (GFs) are widely used in point cloud processing to generate digital terrain models. To enhance the accuracy and robustness of ground filtering for airborne point clouds, we propose a data-driven morphological filtering algorithm (DMF). DMF begins by identifying near-ground voxel centroids after voxelizing the input point clouds. Next, a digital elevation model is constructed based on the elevation information of these near-ground voxel centroids. A composite morphological filter is then designed to identify ground and non-ground patches within the digital elevation model before labeling their inner near-ground voxel centroids as GF-support nodes. The composite morphological filter is used to recognize non-ground areas with incomplete edge structures depicted in the input point cloud and to correct misclassified areas. Finally, a bidirectional k-dimensional tree search engine is built between the GF-support nodes and the input point cloud to separate ground and non-ground points. Experimental results show that DMF achieves ground filtering accuracy with an average F-score greater than 0.88, demonstrating robustness in generating digital terrain models across various test scenarios. Furthermore, the intermediate outputs of DMF enable instance segmentation of artificial objects in airborne point clouds. 
![GA0926](https://github.com/user-attachments/assets/fa48f66d-1233-43f2-adf2-91b795a3be90)

### DMF Algorithm Software Usage Instructions
To reduce the difficulty of using the DMF algorithm, **prevent the source code from being improperly modified and used for commercial purposes without permission**, we provide an EXE program of the software corresponding to this algorithm. You can directly open and run it, then select the folder where the point cloud CSV files to be processed are stored before running the software. The software will read the point clouds from the folder one by one and perform ground filtering using the DMF.

The ground filtering result of a single point cloud file will be saved in the folder specified by the user. Since DMF is a data-driven ground filtering algorithm, **users do not need to customize any parameters** during the analysis of each point cloud CSV file. It should be noted here that:
> **The CSV file format must be (X, Y, Z,...)**. The DMF program will only read the first three columns of the point cloud file and assign them as XYZ coordinates respectively, and the subsequent attributes will not participate in the analysis.

The processing process and progress will be displayed in the status bar at the bottom of the software.

During the operation of the DMF algorithm, non-ground node label results will be output, which can be used as an unsupervised instance segmentation engine for non-ground objects to support users' specific applications. Therefore, we have set a checkbox in the software:
- ✅ **Checked**: The intermediate file (non-ground node label results) will be output.
- ❌ **Unchecked**: Only the ground filtering result of the input point cloud will be output (default).

We provide some sample CSV data to help you prepare your own data for processing with the DMF software. Should you encounter any usage issues, please feel free to contact us in a timely manner.
The DMF algorithm has currently applied for a Chinese national invention patent (pending authorization). If you need the source code of DMF, please contact us and provide the reasons for your application. Since the software provided by this project is free for use, we will not share the source code in principle to avoid disputes related to intellectual property rights.

The average accuracy of GFs for test point clouds. The evaluation metrics for the GF results include overall ground filtering accuracy (ACC), IOU1, IOU2, F-score, and Cohen's Kappa coefficient (Kappa), all with a range of [0, 1]. The colored points indicate the ground filtering accuracy for each test point cloud, and diamond dots representing the average evaluation metrics of test point clouds in the same scenario.
![1-s2 0-S2667393225000213-gr7_lrg](https://github.com/user-attachments/assets/b80e2902-cbb7-4888-b1dc-d77b3a45354f)

The ground filtering results and accuracy of some point clouds using test GFs. The FSC means the F-score.
![FIG8(0925)](https://github.com/user-attachments/assets/59022fe6-31d7-4f39-8d07-e5eddc7c6eda)

Error distribution in the DTM generated from ground points extracted by the tested GFs. 
![1-s2 0-S2667393225000213-gr10_lrg](https://github.com/user-attachments/assets/e0dfd7b9-ac0b-4391-aae6-fe867d5801e9)
