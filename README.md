# Data Preparation for Public Health Organization - OpenClassrooms Project P3 - Engineer IA

Hello,

The Open Food Facts dataset is available on the [official website](https://world.openfoodfacts.org/) (or can be downloaded from [this link](https://world.openfoodfacts.org/data)). The variables are defined at [this address](https://world.openfoodfacts.org/data/data-fields.txt). The fields are separated into four sections:

1. **General information about the product sheet:** name, modification date, etc.
2. **A set of tags:** product category, location, origin, etc.
3. **Ingredients composing the products and their possible additives.**
4. **Nutritional information:** quantity in grams of a nutrient per 100 grams of the product.

To simplify your approach, I propose starting by establishing the feasibility of suggesting missing values for a variable where more than 50% of the values are missing.

## Steps to Clean and Explore the Data:

### Data Processing
1. **Identify relevant variables** for future processing and necessary for suggesting missing values.
2. **Clean the data by:**
   - Highlighting any missing values among the selected relevant variables, with at least 3 methods of treatment adapted to the concerned variables.
   - Identifying and treating any outliers of each variable.
3. **Automate these processes** to avoid repeating these operations. Note that the client wants the program to function if the database is slightly modified (e.g., adding entries).

### Visualization and Univariate Analysis
1. **Produce visualizations** throughout the analysis to better understand the data.
2. **Perform univariate analysis** for each interesting variable to summarize its behavior. Note that the client requests a presentation that explains the analyses made to a lay audience. Therefore, pay attention to readability: text size, color choices, sufficient sharpness, and vary the graphics (box plots, histograms, pie charts, scatter plots, etc.) to best illustrate your points.

### Variable Selection/Creation using Multivariate Analysis
1. **Perform appropriate statistical tests** to verify the significance of the results.

### Report Writing
1. **Write an exploration report** and a conclusion to explain the feasibility of the requested application.

### GDPR Compliance
1. Even if the data does not include personal information, **explain in a presentation** how this project complies with the 5 main principles of GDPR. Santé publique France would like to publish something on the Open Food Facts website to address questions about GDPR compliance that they sometimes receive.

Please proceed with these steps to prepare the data for the public health organization's analysis.

## Data Cleaning and Objectives

The project is conducted for educational purposes, and the requirements may not necessarily be approached in the same manner in a professional context. The primary goal is to acquire and practice techniques.

### Determining Objectives and Implementation of Data Cleaning
- **CE1**: You have defined the objectives of your data cleaning in relation to the business issue.
- **CE2**: You have defined your approach to data preparation and cleaning.

### Cleaning of Structured Data
- **CE1**: You have eliminated variables that are not relevant to the application's issues.
- **CE2**: You have proposed and justified at least three methods for handling missing values, tailored to the concerned variables (median, setting to zero, IterativeImputer, KNN, deletion, etc.).
- **CE3**: You have identified, quantified, and treated outliers for each variable, taking into account the business context.
- **CE4**: You have addressed duplicates in variables and records.
- **CE5**: You have implemented automation of certain treatments, using appropriate functions and methods.
- **CE6**: You have ensured compliance with GDPR norms during the cleaning operations.

## Statistical Analysis

### Univariate, Bivariate, and Multivariate Analysis
- **CE1**: You have highlighted and statistically analyzed potential outliers.
- **CE2**: You have correctly characterized the observed distributions (unimodal, bimodal, multimodal).
- **CE3**: You have used appropriate metrics (mean or median depending on dispersion).
- **CE4**: You have correctly defined the term "quantiles".

### Bivariate and Multivariate Statistical Analysis
- **CE5**: You have presented and analyzed at least three bivariate analysis graphs.
- **CE6**: You have explained, justified, and applied at least one method of descriptive multivariate analysis.
- **CE7**: You have explained, justified, and applied at least one method of explanatory multivariate analysis.

## Data Representation Through Graphics
- **CE1**: You have identified cases where it was necessary to create a graph.
- **CE2**: You have created readable graphs.
- **CE3**: You have implemented at least one of each of the following types of graphs: boxplot, barplot, pie chart, histogram, scatter plot.

## Using the Anaconda Distribution Manager

Anaconda is a popular open-source distribution for Python and R, mainly used for scientific computing and data science. Its goal is to simplify package management and deployment. Package versions are managed through the package manager, conda.
To install Anaconda, download the installer from [Anaconda's website](https://www.anaconda.com/products/distribution) and follow the installation guide provided. You can choose between different installers tailored for your operating system.
Using Miniconda for a Lightweight Alternative
Miniconda is a minimal version of Anaconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages. If you prefer to have more control over your environment and are mindful of space, Miniconda may be the right choice for you.
Installation: Visit the [Miniconda repository](https://docs.conda.io/en/latest/miniconda.html) on GitHub or [Miniconda's website](https://docs.conda.io/en/latest/miniconda.html) to download and follow the installation instructions.
Creating a Virtual Environment for Each Project
It's best practice to create a new virtual environment for each of your projects to avoid conflicts between package versions. To create a new virtual environment, you can use the following command in your terminal

## Or You Can Use Google Colab

Google Colab is a free cloud service that provides a Jupyter notebook environment for Python developers. It allows you to write and execute Python code in the browser, with no setup required and free access to GPUs.

To get started with Google Colab, visit the [Google Colab website](https://colab.research.google.com/). You can create a new notebook, upload an existing notebook, or collaborate with others in real-time.

## Features

Google Colab provides a range of features, including code execution, text, images, hyperlinks, and more. You can also install additional libraries, access files from Google Drive, and use GPU acceleration.

## Utilizing Google Drive for Flexible File Access

For this project, the approach chosen is to integrate Google Drive for flexible file access in both Anaconda environments running locally (like in PyCharm) and Google Colab.

- **In PyCharm**: You can access data stored in Google Drive by mounting the drive on your system or by syncing files locally.

- **In Google Colab**: Mounting Google Drive is straightforward using the following code snippet, which integrates your Drive files directly into your Colab environment:

## The code adapts to both local (e.g. Pycharm IDE) and Google Colab environments:
"""
This code snippet adapts to both local and Google Colab environments. 

To use it in Google Colab, follow these steps:
1. Create a Gmail account and sign in to Google Drive.
2. Import this notebook into Google Colab.
3. Before running the notebook, create a folder named "OC_IA_P3_Prepare_data_for_a_public_health_organization" in your Google Drive.
4. Execute the cell that allow to detect if the notebook is being run on Google Colab (which is on the notebook) to mount Google Drive and detect the environment if necessary.
5. Place the CSV file "fr.openfoodfacts.org.products.csv" in the "data" subfolder within the project folder. 
6. Run the notebook cells to load and analyze the data.
"""
## Explanation of Using Intermediate CSV Files

In this notebook, we have chosen to use intermediate CSV files at key stages of the data processing pipeline. This approach involves creating new CSV files as output from specific cells and then using these files as input in subsequent cells. The reasons for this choice are as follows:

1. **Avoid Re-running All Cells**:
   By saving the intermediate results to CSV files, we can avoid re-running all the cells in the notebook every time we make a change. This significantly reduces the execution time and allows for more efficient debugging and iterative development.

2. **Efficient Debugging and Iterative Development**:
   With intermediate CSV files, we can isolate and test specific sections of the code independently. If there is an error in a particular step, we can focus on fixing that step without having to re-execute the entire notebook. This modular approach speeds up the development process and makes debugging more manageable.

3. **Consistency and Reproducibility**:
   Saving intermediate results ensures that the results are consistent across different runs. This is particularly useful when working in collaborative environments or when sharing the notebook with others. The intermediate files act as checkpoints, making it easier to reproduce the results without having to rely on in-memory data.

4. **Flexibility in Data Handling**:
   While we have chosen to create intermediate CSV files, another valid approach is to keep the new DataFrames in memory at each stage of the process. This approach also has its advantages, such as reducing I/O operations and potentially faster access to data. However, it may require more careful management of memory and data dependencies.

5. **Balancing Trade-offs**:
   The decision to use intermediate CSV files is a balance between execution efficiency and memory usage. By saving DataFrames to disk, we free up memory and ensure that the notebook can handle larger datasets. However, for smaller datasets or faster iterations, keeping data in memory might be more efficient.

Overall, the use of intermediate CSV files in this notebook is a strategic choice to optimize the development workflow, ensure reproducibility, and manage data efficiently during the data processing pipeline.

## Project Repository

The complete project can be found on GitHub at the following link: [OC_IA_P3_Prepare_data_for_a_public_health_organization](https://github.com/preudh/OC_IA_P3_Prepare_data_for_a_public_health_organization).
