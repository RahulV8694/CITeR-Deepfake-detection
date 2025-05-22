DeepFaceLab | Model: LIAE.f.128.80.48.16
This repository documents my custom-trained DeepFaceLab model using the LIAE architecture with high-resolution face extraction, optimized for production-ready deepfake pipelines. The model has been trained for 1,000,000 iterations on a GeForce RTX 2080 Ti, ensuring convergence and generalization across a wide variety of facial expressions and lighting conditions.


📌 Model Architecture Overview
Architecture: LIAE – Light-Improved Autoencoder, suitable for efficient facial encoding and decoding.

Face Type: f – Full face model (including forehead and chin), ideal for high fidelity swaps.

Resolution: 128x128 – Balanced choice for performance and detail.

Iteration Count: 1,000,000 – Ensures convergence and stability during inference.

🧠 Technical Configuration
Parameter	Value	Description
archi	liae	LIAE architecture (multi-decoder encoder-decoder).
face_type	f	Full-face training to maximize realism.
ae_dims	128	Autoencoder latent space dimensionality.
e_dims	80	Encoder capacity – controls feature richness.
d_dims	48	Decoder capacity for final face generation.
d_mask_dims	16	Mask decoder dimensions – enhances blending.
masked_training	True	Applies binary face masks for training stabilization.
learn_mask	True	Learns facial boundaries explicitly.
eyes_prio	True	Prioritizes eye-region detail for realism.
gan_power	0.0	GAN training disabled (focuses on reconstruction).
random_warp	True	Data augmentation using warps.
random_flip	True	Enables horizontal flips for generalization.
batch_size	8	Training batch size.
pretrain	True	Pretrained base used for warm start.
write_preview_history	False	Live previews only.
clipgrad	False	Gradient clipping disabled.
target_iter	1,000,000	Final iteration target.

⚙️ Training Environment
GPU: NVIDIA GeForce RTX 2080 Ti

VRAM: 11GB

OS: Windows 10 (DeepFaceLab GPU build)

Framework: DeepFaceLab (Latest fork by iperov)

CUDA/CuDNN: CUDA 11.x, cuDNN 8.x

🧪 Use Case
This model is optimized for:

High-fidelity face swaps

Biometric research and spoof testing

Digital doubles for VFX

Academic investigation of generative models

📦 Files & Structure
plaintext
Copy
Edit
workspace/
├── aligned/           # Aligned source face images
├── model/             # Trained model weights
│   ├── d_encoder.h5
│   ├── d_decoder.h5
│   ├── inter_AB.h5
│   ├── inter_BA.h5
│   └── ...
├── data_dst/          # Destination face images
├── result/            # Inference output
📊 Training Performance
Metric	Value
Iterations	1,000,000
Final Loss	~0.020–0.035
Preview Quality	Excellent
Swap Consistency	High

🎓 Future Work
Fine-tune with GAN enabled (gan_power > 0) for hyperrealism

Train with ct_mode: 'hist_match' for lighting consistency

Benchmark LIAE vs SAEHD vs DFL-H128 on perceptual realism metrics

🧑‍💻 Author
Rahul Vijaykumar
Machine Learning Engineer | Biometric Researcher
