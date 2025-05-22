# YourAmbiance Project

## 1) Hugging Face Hub Token is needed for pyannote to operate.

This project uses `pyannote.audio` for speaker diarization and segmentation. To use `pyannote.audio` models from the Hugging Face Hub, you **must** obtain a Hugging Face Hub API token and explicitly accept the user conditions for the specific models.

**1. Obtain a Hugging Face Hub API Token:**
   * Go to [Hugging Face Hub settings](https://huggingface.co/settings/tokens).
   * Generate a new token with at least "read" access.

**2. Accept Pyannote.audio Model User Conditions:**
   * Before you can download and use the `pyannote.audio` models, you need to visit their model pages on Hugging Face Hub and **accept their user conditions**. This is a one-time step per model.
   * **Crucially, visit and accept the conditions for these models:**
     * `pyannote/speaker-diarization-3.1`: [https://huggingface.co/pyannote/speaker-diarization-3.1](https://huggingface.co/pyannote/speaker-diarization-3.1)
     * `pyannote/segmentation-3.0`: [https://huggingface.co/pyannote/segmentation-3.0](https://huggingface.co/pyannote/segmentation-3.0)

**3. Set up your `.env` file:**
   * In the root directory of this project, create a new file named `.env`.
   * Add your Hugging Face Hub token to this file in the following format:

     ```
     HF_TOKEN=hf_YOUR_PERSONAL_HUGGINGFACE_TOKEN_HERE
     ```
     (Replace `hf_YOUR_PERSONAL_HUGGINGFACE_TOKEN_HERE` with the actual token you obtained.)

**Important Security Note:** The `.env` file is intentionally ignored by Git (see `.gitignore`) to prevent your personal token from being committed to the repository. **Never commit your `.env` file.**

Once these steps are completed, the application will be able to load and use the `pyannote.audio` models for speaker diarization.

## 2) Temporary Files

This project utilizes a dedicated temporary directory for its operations. This directory is named `YourAmbianceTemp` and is created within your system's default temporary file location (e.g., `/tmp/YourAmbianceTemp` on Linux, `C:\Users\YourUser\AppData\Local\Temp\YourAmbianceTemp` on Windows).

Files within `YourAmbianceTemp` are managed automatically by the application during runtime. You generally do not need to interact with this directory directly.
