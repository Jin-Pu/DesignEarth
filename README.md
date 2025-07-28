# DesignEarth: A Multimodal Dataset for Controllable Aerial Image Generation

![DesignEarth Logo](https://example.com/path/to/logo.png) *(placeholder for actual logo image)*
[![Home](https://img.shields.io/badge/Home-DesignEarth-blue)](https://github.com/DesignEarth) 
[![Paper](https://img.shields.io/badge/Paper-PDF-red)](https://arxiv.org/abs/XXXX.XXXXX) 
[![HuggingFace](https://img.shields.io/badge/%F0%9F%A4%97-HuggingFace-yellow)](https://huggingface.co/datasets/DesignEarth)
[![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/DesignEarth/DesignEarth)
## Overview
The **DesignEarth** dataset addresses a critical gap in aerial imagery research by providing the first large-scale multimodal resource that integrates:
- 265,247 georeferenced high-resolution (1.2m) aerial images
- 1,060,988 corresponding condition images (4 types per aerial image)
- 530,494 semantic descriptions (38.4M+ tokens)

Developed by Pu Jin and team, this dataset enables breakthroughs in **controllable aerial image generation** through synergistic multi-modal inputs.

## Key Features

### Multi-Modal Composition
Each data entry contains:
1. **High-res aerial image** (1.2m resolution)
2. **Condition images**:
   - Map images (from OpenStreetMap)
   - Pencil sketches
   - Canny edge maps
   - Lineart representations
3. **Semantic descriptions**:
   - Long and short captions
   - Model-generated + human-refined (using Florence-2)

![Sample Entries](https://example.com/path/to/figure3.png) *(Figure 3 from paper showing multi-modal samples)*

### Geographic Diversity
- Sourced globally via Google Earth Engine
- Covers urban/rural landscapes, natural environments, and industrial sites
- Balanced distribution across multiple countries *(see Figure 1 in paper)*

| Country | Number of Images |
|---------|------------------|
| United States | 110,325 |
| Japan | 61,252 |
| Australia | 23,715 |
| France | 18,180 |
| Brazil | 15,810 |
| Germany | 13,466 |
| Saudi Arabia | 11,385 |
| Spain | 7,695 |
| Italy | 3,419 |

## Benchmark Results

### Text-to-Image Generation
| Type | Model | #Params | FID ↓ |
|------|-------|---------|-------|
| Diffusion | LDM-4 | 400M | 57.26 |
| Diffusion | DiT-XL/2 | 675M | 54.12 |
| AR | LlamaGen-XXL | 1.4B | 50.47 |
| AR | Infinity-2B | 2.0B | 48.75 |
| AR | **RAR-XL** | 1.5B | **47.53** |

### Controllable Generation
| Type | Method | Map | Pencil | Canny | Lineart |
|------|---------|-----|--------|-------|---------|
| Diffusion | ControlNet | 54.12 | 45.68 | 48.76 | 50.34 |
| Diffusion | ControlNet++ | 50.47 | 46.01 | 47.63 | 43.87 |
| Diffusion | UniControl | 51.26 | 44.08 | 46.57 | 49.12 |
| AR | ControlVAR | 48.75 | **42.85** | 45.80 | **45.33** |
| AR | ControlAR | **47.12** | 43.78 | **42.15** | 46.67 |

## Applications
- Controllable aerial scene synthesis
- Map-to-image generation
- Remote sensing analysis:
  - Building footprint detection
  - Semantic segmentation
  - Scene classification
  - Image captioning
