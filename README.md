DMF: A Data-Driven Ground Filtering Algorithm for Airborne Point Clouds

Ground Filtering algorithms (GFs) are widely applied in point cloud processing for digital terrain model (DTM) generation. To enhance the accuracy and robustness of ground filtering for airborne point clouds, we propose a Data-Driven Morphological Filtering (DMF) algorithm.

🧠 How Does DMF Work?

DMF achieves accurate separation of ground points and non-ground points through a 5-step core workflow:

1. Voxelization Preprocessing: Voxelize the input point cloud and identify near-ground voxel centroids.

2. DEM Construction: Build a Digital Elevation Model (DEM) using the elevation information of near-ground voxel centroids.

3. Composite Morphological Filtering: Design a customized filtering operator to label ground and non-ground patches in the DEM.

4. GF-support Node Labeling: Mark near-ground voxel centroids as GF-support nodes (this step corrects misclassified areas and captures incomplete edge structures).

5. Bidirectional k-d Tree Search: Establish a search mechanism between GF-support nodes and input point clouds to finalize ground/non-ground point separation.

📊 Impressive Experimental Results

Experimental verification shows that DMF performs excellently, earning it the title of "star algorithm" in the field of ground filtering:

- Average F-score for ground filtering accuracy > 0.88

- Strong robustness across multiple test scenarios

- Added Value: Intermediate output supports instance segmentation of man-made objects in airborne point clouds

💻 DMF Software User Guide

We provide an EXE executable program to: lower the threshold for using DMF, and prevent improper modification of the source code and unauthorized commercial use.

🚶 Quick Start Steps

A. Quick Start Steps: Double-click the EXE file to launch the software (no installation required, ready to use 🎉)

B. Select the folder where your point cloud CSV files are stored

C. Click the "Run" button; the software will automatically traverse and read point cloud files one by one, and execute DMF ground filtering

D. Monitor the processing progress in real-time through the status bar at the bottom

⚙️ Key Notes

- Zero Parameter Tuning: DMF adopts a data-driven mechanism, requiring no manual parameter adjustment

- CSV Format Specifications (MUST FOLLOW!): The file must follow the (X, Y, Z, ...) format

- The program only reads the first 3 columns as XYZ coordinates; additional attributes will be automatically ignored

- Intermediate Output Checkbox Function:
  
- ✅ Checked: Output intermediate files (non-ground node labeling results) for instance segmentation tasks

- ❌ Unchecked: Only output ground filtering results (default mode)

📁 Free Sample Data

We have prepared CSV-format sample data to help you quickly adapt your own datasets to the DMF processing workflow. Feel free to download and test!

📞 Support & Legal Information

🆘 Technical Support

If you encounter any issues during use, please contact us promptly—we will provide full assistance.

📜 Patent Status

The DMF algorithm has applied for a Chinese national invention patent (pending authorization).

🔐 Source Code Policy

- Source Code Policy: This software is free for all users

- To avoid intellectual property disputes, the source code is not publicly available by default

- If you truly need the source code, please contact us and provide a detailed application reason


The ground filtering results and accuracy of some point clouds using test GFs. The FSC means the F-score.
![FIG8(0925)](https://github.com/user-attachments/assets/59022fe6-31d7-4f39-8d07-e5eddc7c6eda)

Error distribution in the DTM generated from ground points extracted by the tested GFs. 
![1-s2 0-S2667393225000213-gr10_lrg](https://github.com/user-attachments/assets/e0dfd7b9-ac0b-4391-aae6-fe867d5801e9)
