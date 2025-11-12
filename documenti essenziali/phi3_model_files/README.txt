Phi3 Mini Model Files
=====================

This folder contains all files for the Ollama phi3:mini model copied from ~/.ollama/models/

File List:
----------
1. phi3_mini_model.blob (2.0 GB)
   - Main model file in GGUF format with Q4_0 quantization
   - This is the actual neural network weights

2. config.json (483 bytes)
   - Model configuration and metadata
   - Format: GGUF (GGML Unified Format)
   - Model family: Phi3
   - Model type: 3.8B parameters
   - File type: Q4_0 quantization

3. manifest.json (1.1 KB)
   - Ollama manifest file with all component digests and metadata
   - References all blob files by their SHA256 hashes

4. Modelfile.txt (1.5 KB)
   - Complete Ollama modelfile with template and parameters
   - Can be used to recreate the model: ollama create phi3:mini -f Modelfile.txt

5. template.txt (148 bytes)
   - Chat template for the model
   - Defines how system/user/assistant messages are formatted

6. params.txt (78 bytes)
   - Model generation parameters (stop tokens)

7. license.txt (1.1 KB)
   - MIT License text from Microsoft

Model Specifications:
---------------------
- Architecture: Phi3
- Parameters: 3.8B
- Context Length: 131,072 tokens (128K)
- Embedding Length: 3,072 dimensions
- Quantization: Q4_0 (4-bit quantization)
- Format: GGUF (Ollama-specific)
- Total Size: ~2.0 GB on disk
- License: MIT License (Microsoft Corporation)

Usage Notes:
------------
⚠️  These files are in Ollama's GGUF format, not HuggingFace format.

To use with Ollama (local):
  ollama create phi3:mini -f Modelfile.txt

To use with HuggingFace transformers (different format):
  You would need to download from: microsoft/phi-3-mini-4k-instruct
  or microsoft/phi-3-mini-128k-instruct

The model uses these stop tokens:
- <|end|>
- <|user|>
- <|assistant|>
