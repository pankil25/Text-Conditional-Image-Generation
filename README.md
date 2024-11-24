# Hierarchical Text-Conditional Image Generation Using CLIP Latents  

This project demonstrates a **hierarchical text-conditional image generation pipeline** implemented in a single Jupyter Notebook. The notebook utilizes **CLIP embeddings** and the **WebDataset format** for efficient data handling and image generation.  

---

## Workflow  

The following steps outline the hierarchical text-to-image generation process:  

1. **Text Encoding with CLIP**  
   - Input text is processed using **CLIP's text encoder**, producing a semantic representation in a shared latent space.  

2. **Mapping Text to Image Embeddings**  
   - A **prior model** maps text embeddings into the image embedding space of CLIP, ensuring semantic alignment.  

3. **Image Decoding**  
   - A **decoder model** generates images based on the mapped embeddings. This model uses progressive methods to improve resolution and quality.  

4. **WebDataset Integration**  
   - Text and image pairs are handled using **WebDataset**, enabling efficient data loading and scaling for large datasets.  

---

## Features  

- **WebDataset Support**: Handles datasets stored as `.tar` archives, simplifying scalability.  
- **CLIP Integration**: Utilizes pre-trained CLIP models for text and image embedding alignment.  
- **Single Notebook Workflow**: All components, from data loading to inference, are implemented in a single `.ipynb` file.  
- **Hierarchical Decoding**: Generates progressively refined, high-quality images.  

---

## Dataset Preparation  

### WebDataset Format  
Prepare your data in the WebDataset format, where each `.tar` file contains paired `.jpg` (images) and `.txt` (text descriptions).  

**Example Archive Structure:**  

shard-00000.tar
├── sample_00000.jpg
├── sample_00000.txt
├── sample_00001.jpg
├── sample_00001.txt
└── ...


Usage
1. Open the Notebook
Open the provided Jupyter Notebook file (improve-dalle2-part-3-75-dataset.ipynb) in your environment (e.g., Jupyter Lab, Colab, or Kaggle).

2. Install Dependencies
Install required Python packages:

bash
Copy code
pip install webdataset clip-by-openai torch torchvision tqdm  
3. Configure Paths
Set the path to your WebDataset .tar files in the notebook.
Specify hyperparameters like batch size, learning rate, and latent dimensions in the configuration cells.
4. Run Training
Execute the cells in sequence to:

Load the WebDataset shards.
Encode text descriptions into CLIP embeddings.
Train the prior model to map text embeddings to image embeddings.
Train the decoder model for image generation.
5. Generate Images
Run the inference section of the notebook to generate images from textual descriptions.

Example Text Input:

arduino
Copy code
"A futuristic cityscape with flying cars and neon lights."  
Generated Output:
An image that visually represents the text input.

