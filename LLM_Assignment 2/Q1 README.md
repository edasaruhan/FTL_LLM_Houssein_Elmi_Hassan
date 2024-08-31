# Text Generation Application Using GPT-2

# Overview
This project is a basic text generation application that uses the GPT-2 model to generate text based on user-provided prompts. The focus of this project is on generating text related to the United Nations Sustainable Development Goals (SDGs). The application was built as part of an assignment to explore the capabilities of open-source generative AI models.

# Installation
To run this project, you need to have Python installed. You’ll also need to install a few libraries:

- Clone the repository or download the code files.
- Install the required Python packages:

! pip install transformers torch

# How to Use
- Run the script.
- You’ll be prompted to enter a sentence to start with.
- The GPT-2 model will generate the rest of the text based on your input.
- The generated text will be printed on the screen.

# Example Usage:

- Run the script
- python Q1_Text_Generation_Application.py

# Example
Type a sentence to start with: Eradicating poverty in all its forms remains one of the greatest challenges facing humanity. By 2030, the aim is to

# Output
Here's what GPT-2 came up with:
Eradicating poverty in all its forms remains one of the greatest challenges facing humanity. By 2030, the aim is to develop the world's poorest nations...
Code Explanation

Loading the Model and Tokenizer:

from transformers import GPT2LMHeadModel, GPT2Tokenizer

tokenizer = GPT2Tokenizer.from_pretrained("gpt2")
model = GPT2LMHeadModel.from_pretrained("gpt2")
This code loads the GPT-2 model and tokenizer, which are used to process and generate text.

# Generating Text:

prompt = input("Type a sentence to start with: ")
input_ids = tokenizer.encode(prompt, return_tensors="pt")
output = model.generate(input_ids, max_length=100, do_sample=True, temperature=0.7)
generated_text = tokenizer.decode(output[0], skip_special_tokens=True)
print("Here's what GPT-2 came up with:")
print(generated_text)

After the user inputs a prompt, the model generates text based on that prompt. The temperature parameter controls the randomness of the output.

# Known Issues
- Inaccurate Information: Sometimes the model generates text that is factually incorrect or irrelevant to the prompt.
- Repetitive Text: The model may produce repetitive or nonsensical sentences, especially for longer text generations.

# Future Improvements
- Fine-Tuning the Model: Training the model on specific data related to SDGs might improve the accuracy and relevance of the generated text.

# Contributors
Houssein Elmi Hassan
