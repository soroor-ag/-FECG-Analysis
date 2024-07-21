# -FECG-Analysis
TS and FastICA FECG Analysis and Annotation
# Extraction of FECG from AECG using TS and FastICA

This project implements Template Subtraction (TS) and Independent Component Analysis (ICA) using the FastICA algorithm to extract fetal electrocardiogram (FECG) signals from abdominal electrocardiogram (AECG) signals. The project involves preprocessing the AECG signals, applying TS and FastICA to remove maternal ECG components, and annotating fetal QRS complexes.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Functions](#functions)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/fecg-extraction.git
    cd fecg-extraction
    ```

2. **Create and activate a virtual environment (optional but recommended):**
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. **Install the required packages:**
    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. **Prepare your dataset:**
    - Ensure your dataset is in the WFDB format and located in a directory (e.g., `set-a/`).
    - Update the `set_name` variable in the code to point to your dataset directory.

2. **Run the script:**
    ```bash
    python main.py
    ```

3. **View the results:**
    - Annotation files will be saved in the same directory as the input records with the suffix specified in `annotation_suffix`.

## Functions

### preprocessing
Preprocesses the ECG signal by applying a bandpass filter to remove noise.

### MECGcancellation
Removes the maternal ECG components from the signal using the identified peaks.

### PeakDetection
Identifies peaks in the ECG signal which correspond to QRS complexes.

### find_mecg_component
Identifies the component corresponding to the maternal ECG.

### remove_component_and_reconstruct
Removes a specified component and reconstructs the mixed signal without it.

### process_records
Processes all records in the dataset, applies FastICA, removes maternal ECG components, annotates fetal QRS complexes, and saves the annotations.

## Results

The results of the analysis include:
- Annotated fetal QRS complexes saved as WFDB annotation files.
- Description files detailing the process and results.

## Contributing

Contributions are welcome! If you have any improvements or bug fixes, please submit a pull request.

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -m 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to update the project details and add any additional information as needed. If you encounter any issues or have questions, please open an issue in the GitHub repository.

