# Bria AI Training Project

This project fine-tunes a Llama 3.1 8B model to respond as "Bria" based on Google Voice message history.

## Project Structure
- `Calls/`: Contains the Google Voice export (HTML files).
- `Calls/training_output/`: Contains the parsed and formatted training data.
- `Calls/scripts/`:
    - `parse_google_voice_export.py`: Extracts conversations from HTML.
    - `format_for_finetune.py`: Formats data for Chat fine-tuning.
    - `train_local.py`: Local training script for RTX 4070 (8GB VRAM).
    - `test_bria_ai.py`: Tester script using OpenAI API.
    - `test_bria_local.py`: Tester script for local GGUF model (via Ollama).
- `Bria_AI_Training.ipynb`: Pre-configured Google Colab notebook.

## Local Training (RTX 4070)
The training environment is set up in the `train_env` virtual environment.
To run training:
```powershell
.\train_env\Scripts\activate
python Calls/scripts/train_local.py
```

## Running the Assistant
Once training is finished and exported to GGUF:
1. Install Ollama.
2. Run `ollama create bria -f Modelfile`.
3. Run `python Calls/scripts/test_bria_local.py`.

## Business Rules (Online Only)
- Focused EXCLUSIVELY on Online Services.
- FaceTime Shows: $50 / 20 mins.
- Video Chats: $65 / 25 mins.
- Sexting: $60.
- Payment Upfront via Apple Pay, CashApp, PayPal, or Venmo.
- No in-person meetups or outcalls.
