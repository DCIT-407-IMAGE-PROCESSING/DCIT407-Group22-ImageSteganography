# Group 22 — DCIT 407 Presentation Outline & Live Demo Script
**Format:** 10-Minute Presentation + 5-Minute Q&A  
**Repository:** `DCIT407-Group22-ImageSteganography`

---

## 10-Slide Outline (Target: ~10 Minutes Total)

### Slide 1: Title & Group 22 Overview (0:30)
- **Visuals:** Project title, DCIT 407 course label, Group 22 name, member names/roles, and repository reference.
- **Key Talking Points:** Introduce the topic (Image Steganography) and state what the team built from first principles in NumPy alongside a comparative evaluation.

### Slide 2: Problem Statement & Core Trade-Offs (0:45)
- **Visuals:** Simple diagram showing Cover Image + Secret Payload + Key/Algorithm -> Stego Image -> Extracted Payload.
- **Key Talking Points:** Explain covert data hiding vs. encryption, and highlight the three classic constraints: imperceptibility, payload capacity, and robustness/detectability.

### Slide 3: Dataset & Experimental Setup (0:45)
- **Visuals:** Summary card of test dataset (number of images, formats/resolutions, public/licensed source) and Python stack (`numpy`, `opencv-python`, `matplotlib`, `scikit-image`, `scipy`, `pandas`).
- **Key Talking Points:** Describe the images used for testing and confirm reproducibility using a clean Python virtual environment.

### Slide 4: First-Principles Method in NumPy (1:15)
- **Visuals:** Clean step-by-step flow of bit manipulation / embedding & extraction logic in NumPy arrays.
- **Key Talking Points:** Walk through how payload bytes/bits (and message length/header) are embedded and extracted directly using NumPy array operations without relying on pre-built steganography libraries.

### Slide 5: Comparison Method / Parameter Variant (1:00)
- **Visuals:** Side-by-side comparison diagram or parameter table (e.g., primary setting vs. alternative bit-depth, ordering/key strategy, or secondary method).
- **Key Talking Points:** Explain what second method or parameter setting was tested and why it was chosen to evaluate trade-offs.

### Slide 6: Live Demo — Embed, Visual Check & Extract (2:00)
- **Visuals:** Live terminal output and generated cover vs. stego / difference preview.
- **Key Talking Points:** Follow the Live Demo Script below to demonstrate end-to-end embedding, visual inspection, and lossless extraction.

### Slide 7: Visual Results — Cover, Stego & Difference Maps (1:00)
- **Visuals:** High-resolution image grid from `results/` showing Cover Image, Stego Image, and amplified pixel difference (`|Cover - Stego| * k`).
- **Key Talking Points:** Point out perceptual similarity at lower payloads and show where pixel changes occur in the difference map.

### Slide 8: Quantitative Evaluation & Comparison (1:15)
- **Visuals:** Metrics table and chart from `results/` comparing PSNR (dB), SSIM, Bit Error Rate (BER), payload capacity (bpp), and runtime.
- **Key Talking Points:** Compare the core method against the alternative/parameter setting using concrete numbers rather than intuition alone.

### Slide 9: Limitations, Failure Cases & Robustness (0:45)
- **Visuals:** Examples of degraded/modified stego images or edge cases where extraction degrades or artifacts appear.
- **Key Talking Points:** Be transparent about limitations—such as sensitivity to lossy re-compression (e.g., JPEG), geometric changes, or capacity limits.

### Slide 10: Conclusion, Takeaways & Q&A (0:45)
- **Visuals:** 3 concise takeaway bullets + "Questions & Discussion".
- **Key Talking Points:** Summarize the best trade-off found in experiments, mention possible future improvements, and open the floor for the 5-minute Q&A.

---

## Live Demo Script (Target: 2:00 Max)

### Pre-Demo Checklist (Before Presentation Starts)
- [ ] VS Code is open to `DCIT407-Group22-ImageSteganography` with terminal focused.
- [ ] `.venv` is activated (`.venv\Scripts\Activate.ps1`) and tested once before presenting.
- [ ] Sample cover image is ready in `data/samples/` and output path points cleanly to `results/`.
- [ ] Backup screenshots/outputs are saved in `results/` in case of display or runtime issues.

### Step-by-Step Demo Execution
1. **Embed Secret Message (0:30):**
   - Run the embed command with a short test message and inspect printed metrics (PSNR, SSIM, runtime).
   - *Say:* "First, we embed a sample payload into a cover image in `data/samples/` using our NumPy implementation and log the quality metrics."
2. **Inspect Visual Output (0:30):**
   - Open or display the side-by-side cover vs. stego comparison and amplified difference image from `results/`.
   - *Say:* "Visually, the stego image is indistinguishable from the cover image, while the amplified difference shows the exact locations modified."
3. **Extract & Verify Payload (0:30):**
   - Run the extraction command on the stego image and show the recovered message matching the original input.
   - *Say:* "Next, we extract the hidden message from the stego image and confirm exact recovery with zero bit errors."
4. **Show Parameter / Method Contrast (0:30):**
   - Briefly show or run a higher-payload or alternative parameter setting to highlight the trade-off.
   - *Say:* "Increasing payload/bit-depth boosts capacity, but as our metrics show, it lowers PSNR/SSIM and increases visible/statistical trace."