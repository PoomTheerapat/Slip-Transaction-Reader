# 🧾 Slip Recognition & OCR Tool

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![PaddleOCR](https://img.shields.io/badge/PaddleOCR-v2.6-green?style=for-the-badge)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-red?style=for-the-badge&logo=opencv)
![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)

## 📖 Overview

The **Slip Recognition Project** is a specialized computer vision and OCR pipeline designed to automate the extraction of structured data from bank transaction slips. Built with **Baidu's PaddleOCR** and **OpenCV**, it offers a robust workflow for defining regions of interest (ROIs) on a template and batch-processing images to extract fields like Transaction ID, Date, Amount, and Account Numbers.

This tool is particularly useful for financial data entry automation, reconciliation processes, and digital archiving.

## ✨ Key Features

*   **Interactive ROI Selector**: A user-friendly tool to visually draw and label regions of interest on a master template.
*   **Resolution Independence**: Automatically normalizes ROI coordinates to handle input images of varying resolutions.
*   **High-Accuracy OCR**: Utilizes PaddleOCR (with GPU support) for robust text detection and recognition, specifically tuned for Thai and English.
*   **Batch Processing**: Process hundreds of slip images in one go.
*   **Structured Output**: Exports results to both JSON (for API/Web integration) and CSV (for Excel/Analysis) formats.

## 📂 Project Structure

```text
slip_recognition/
├── configs/                # Configuration files for ROI definitions
│   ├── roi_config.json
│   └── roi_config_normalized.json
├── data/
│   ├── processed/          # Generated output (OCR results)
│   ├── raw/                # Input images to be processed
│   └── templates/          # Master template image
├── notebooks/              # Interactive Jupyter Notebooks
│   └── 01_interactive_roi_extraction.ipynb
├── src/                    # Source code modules
└── requirements.txt        # Python dependencies
```

## 🚀 Getting Started

### Prerequisites

*   Python 3.8 or higher
*   CUDA-compatible GPU (Recommended for PaddleOCR performance) or CPU

### Installation

1.  **Clone the repository**
    ```bash
    git clone https://github.com/yourusername/slip-recognition.git
    cd slip-recognition
    ```

2.  **Create a virtual environment (Optional but recommended)**
    ```bash
    python -m venv .env
    # Windows
    .env\Scripts\activate
    # Linux/Mac
    source .env/bin/activate
    ```

3.  **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```

## 🛠️ Usage

### 1. Define Regions of Interest (ROI)
If you are setting up a new slip format:
1.  Place your template image in `data/templates/`.
2.  Open the notebook:
    ```bash
    jupyter notebook notebooks/01_interactive_roi_extraction.ipynb
    ```
3.  Run the cells to launch the interactive OpenCV window.
4.  **Draw** boxes around fields and **Name** them in the terminal prompt.
5.  Press **'S'** to save the configuration to `configs/roi_config.json`.

### 2. Run Batch Extraction
1.  Place your raw slip images (`.jpeg`) in `data/raw/`.
2.  Continue running the cells in the notebook (or execute the extraction script if available).
3.  The system will:
    *   Load the normalized configuration.
    *   Apply OCR to each defined region.
    *   Save results to `data/processed/ocr_results.json` and `data/processed/ocr_results.csv`.

## ⚙️ Configuration

The tool relies on two key JSON files in the `configs/` directory:

*   **`roi_config.json`**: Stores absolute pixel coordinates from the template image.
*   **`roi_config_normalized.json`**: Stores relative coordinates (0.0 - 1.0). **This is used for actual processing** to ensure the tool works across different image sizes.

## 📦 Dependencies

*   [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR): Awesome Multilingual OCR toolkits.
*   [OpenCV](https://opencv.org/): Open Source Computer Vision Library.
*   [Pandas](https://pandas.pydata.org/): Data analysis and manipulation.
*   [NumPy](https://numpy.org/): Fundamental package for scientific computing.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1.  Fork the project
2.  Create your feature branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**Author:** [PoomTheerapat]
