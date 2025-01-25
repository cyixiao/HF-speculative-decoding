# HF-speculative-decoding

This repository is a modified version of the Hugging Face `transformers` library. It enhances the speculative decoding feature to include detailed token statistics for the assistant model and the main model.

## Features

- **Assistant Total Tokens**: Total tokens generated by the assistant model (including rejected ones).
- **Assistant Accepted Tokens**: Tokens generated by the assistant model and accepted by the main model.
- **Main Model Tokens**: Tokens generated directly by the main model.

## Usage

With this modification, you can access token statistics directly from the `generate` method's output:

```python
outputs = main_model.generate(
    input_ids=input_ids,
    assistant_model=assistant_model,
    max_length=100,
    return_dict_in_generate=True,
)

print(f"Assistant Total Tokens: {outputs.assistant_total_generated_tokens}")
print(f"Assistant Accepted Tokens: {outputs.assistant_generated_tokens}")
print(f"Main Model Tokens: {outputs.main_model_generated_tokens}")
```

## Installation

Clone this repository and install it locally:
```bash
git clone https://github.com/cyixiao/HF-Speculative-Decoding.git
cd HF-Speculative-Decoding
pip install -e .
```
