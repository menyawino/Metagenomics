# Whole Metagenome Sequencing (WMS) General Pipeline
![image](https://github.com/user-attachments/assets/56206c54-ec2b-4511-8fce-b0bd6b2e0410)
This figure was created using Figma FigJam Board

# Pipeline Overview
The workflow is designed to automate WMS data analysis. It handles raw sequencing data through to the generation of a PDF report including relative abundance of microorganisms, antibacterial resistance report, phylogenetic tree, and disease associations of the microorganisms detected. Snakemake workflow management language is used with design considerations detailed below. The whole workflow uses open-source tools and databases to promote reproducibility.

# Design Considerations
•	Modularization: The pipeline is organized into modular snakemake rules (steps), making it easy to extend or modify specific components without affecting the overall workflow.
•	Containerization: Each rule has a .yml conda environment file with specific tools and versions to ensure workflow reproducibility and isolation from the system. It also avoids tools dependency conflict.
•	Error Handling and Logging: Error handling and logging are to be implemented in snakemake to ensure any issues are promptly identified and addressed.
•	Configurable Parameters: A configuration file will be used to manage tool parameters and paths to enhance user-friendliness, flexibility, and ease of updates.
•	Data Validation and QC: Rigorous QC steps for data validation and integrity checks to ensure the input data meets set standards before proceeding with the next steps.
•	Scalability: Snakemake parallel processing, automatic file chunking, and cloud computing integration can be utilized to scale up the workflow to handle large datasets.
•	Version Control: All tools and dependencies are version-controlled in the conda .yml files and version control system to maintain reproducibility of the analysis.
•	Interactive Visualizations: Interactive visualization tools can be integrated based on visualization preferences (e.g., QIIME2 View) for more detailed exploration of the results.
•	Automated Report Generation: The workflow is designed to finally generate a report with all the requested data in a single PDF file using a visualization R script in a snakemake rule.
