## 🔍 Multi-Embedding Feature Extraction

This project integrates four different medical foundation model families to extract a diverse set of embeddings from both **CT** and **PET** images.  
Each model contributes complementary information such as global semantics, structural patterns, radiology-aligned visual features, and fine-grained radiomic tokens.

A total of **eight embeddings** are produced (four models × CT/PET).

---

### 🧩 1. PET-Diffusion Model
We use the PET-Diffusion architecture to obtain global latent representations:

- Global CT embedding  
- Global PET diffusion embedding  

These features capture modality-specific semantic information learned through diffusion-based reconstruction.

---

### 🩺 2. SAM-Med2D Image Encoder
Using the image encoder of SAM-Med2D, we obtain segmentation-aware structural embeddings:

- CT image embedding  
- PET image embedding  

These embeddings retain organ-level spatial context and structural boundaries.

---

### 🧠 3. MedCLIP Vision Encoder
MedCLIP provides radiology-aligned visual embeddings by aligning medical images with text supervision:

- CT MedCLIP visual embedding  
- PET MedCLIP visual embedding  

These representations incorporate high-level semantic information consistent with radiology reporting.

---

### 🧬 4. RadFM Token-Level Embeddings
RadFM produces dense token-level features that encode radiomics-style local image information:

- CT token embeddings  
- PET token embeddings  

These embeddings capture fine-grained regional and lesion-specific signals.

---

## 📦 Summary of All Embeddings

| Model Type        | CT Output            | PET Output              | Feature Style |
|------------------|----------------------|--------------------------|----------------|
| PET-Diffusion    | CT global embedding  | PET global diffusion embedding | Global semantic representation |
| SAM-Med2D        | CT image embedding   | PET image embedding      | Segmentation-aware structural context |
| MedCLIP          | CT visual embedding  | PET visual embedding     | Radiology-aligned semantic features |
| RadFM            | CT token embeddings  | PET token embeddings     | Fine-grained radiomics tokens |

---

## 🚀 Fusion Module

All embeddings are combined through a multi-branch feature fusion network, enabling the model to leverage:

- global semantic cues  
- organ-level structural information  
- CLIP-aligned radiology knowledge  
- localized radiomics signals  

This integrated feature space strengthens PET-based Hodgkin’s lymphoma classification and improves robustness across centers.
