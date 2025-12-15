# DMF
Ground filtering algorithms (GFs) are widely used in point cloud processing to generate digital terrain models. To enhance the accuracy and robustness of ground filtering for airborne point clouds, we propose a data-driven morphological filtering algorithm (DMF).
🧠 How Does DMF Work?
DMF follows a 5-step superpower workflow to separate ground and non-ground points:
Voxelization First: Voxelize the input point clouds and identify near-ground voxel centroids.
DEM Construction: Build a digital elevation model (DEM) using the elevation info of these centroids.
Composite Morphological Filter: Design a tailor-made filter to spot ground and non-ground patches in the DEM.
GF-support Node Labeling: Mark the inner near-ground voxel centroids as GF-support nodes (this step fixes misclassified areas and captures incomplete edge structures!).
Bidirectional k-d Tree Search: Build a search engine between GF-support nodes and input point clouds to finalize ground/non-ground separation.
📊 Impressive Results
Experimental tests prove DMF is a rockstar:
Average F-score > 0.88 for ground filtering accuracy
Robust performance across various test scenarios
Bonus: Intermediate outputs enable instance segmentation of artificial objects in airborne point clouds!

image
🖥️ DMF Software Usage Instructions
🎯 Core Goal
We provide an EXE program to:
Lower the threshold for using DMF
Prevent source code from improper modification and unauthorized commercial use
🚶 Quick Start Steps
Double-click the EXE file to launch the software (no installation needed! 🎉)
Select the folder where your point cloud CSV files are stored
Click to run the software—it will auto-read point clouds one by one and apply DMF ground filtering
Check the status bar at the bottom to track processing progress
⚙️ Key Tips You Can’t Miss
Zero parameter tuning required: DMF is data-driven, so you don’t need to tweak any settings
CSV format rule (MUST FOLLOW!):
The CSV file must be in (X, Y, Z, ...) formatThe program only reads the first three columns as XYZ coordinates—extra attributes are ignored
Checkbox magic for intermediate outputs:
✅ Checked: Get the intermediate file (non-ground node label results) for instance segmentation tasks
❌ Unchecked: Only output ground filtering results (default mode)
📁 Free Sample Data
We’ve prepared sample CSV data to help you prep your own datasets for DMF processing—grab them and test away!
📞 Support & Legal Stuff
🆘 Need Help?
If you run into any issues while using the software, feel free to contact us timely—we’re here to help!
📜 Patent Status
The DMF algorithm has applied for a Chinese national invention patent (pending authorization).
🔐 Source Code Policy
The software is free for use for all users
Source code is not shared by default to avoid intellectual property disputes
If you really need the source code, contact us and provide a detailed application reason
The ground filtering results and accuracy of some point clouds using test GFs. The FSC means the F-score.
![FIG8(0925)](https://github.com/user-attachments/assets/59022fe6-31d7-4f39-8d07-e5eddc7c6eda)

Error distribution in the DTM generated from ground points extracted by the tested GFs. 
![1-s2 0-S2667393225000213-gr10_lrg](https://github.com/user-attachments/assets/e0dfd7b9-ac0b-4391-aae6-fe867d5801e9)
