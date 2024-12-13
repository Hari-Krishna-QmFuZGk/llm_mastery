# Small Language Model Project

This repository contains a small-scale implementation of a language model built using a custom tokenizer and trained on a subset of text data. This project serves as a hands-on journey for understanding the foundational aspects of building large language models (LLMs) from scratch. It represents my first attempt at creating an LLM, inspired by the Udemy course `LLM Mastery: Hands-on Code, Align and Master LLMs`. Through this project, I explored various facets of LLM development, overcame challenges, and gained insights into the intricate processes involved.

## Key Learnings and Challenges

- **Model Architecture and Training**: Implementing multi-head attention and transformers was a pivotal learning experience. I wrote the building blocks , including Attention mechanism, feedforward layers, using PyTorch. Training was conducted on an NVIDIA GeForce RTX 3080 Ti GPU. While the hardware facilitated faster iterations, limitations in computational power highlighted the importance of resource-efficient model scaling for larger datasets and parameters. Also used custom tokenizer to handle domain-specific terms effectively.

- **Loss Function and Monitoring**: CrossEntropy loss was used to measure training and validation performance. Incorporating Weights & Biases allowed me to monitor progress visually and adapt hyperparameters when necessary. Despite achieving stable training, the small model size limited its capability to generate coherent and meaningful text consistently.

- **Inference and Output**: Testing the model with various inputs provided insights into its strengths and limitations. For instance, generating text such as:

  **Input**: "My self Har"

  **Output**: "My self Harry Birds novel "Baring Mission", but "E and Gasty Hansy Kids vuties of pea than Birds" The Birds of the East and Book Crib at 5.5 million years old. The Birds share the B"

  While promising, the outputs often lacked context or were overly generic, emphasizing the need for scaling.

## Project Structure

```plaintext
├── LICENSE                     # License for the repository
├── README.md                   # Documentation for the repository
├── encoded_data.pt             # Pre-processed and tokenized data for training
├── models
│   └── latest.pt               # The latest checkpoint of the trained model
├── poetry.lock                 # Dependency lock file for Poetry
├── pyproject.toml              # Configuration file for Poetry and dependencies
├── small_llm.ipynb             # Jupyter notebook for experimentation and training
├── wiki.txt                    # Raw dataset used for training the model
├── wiki_tokenizer.model        # Tokenizer model generated from the dataset
└── wiki_tokenizer.vocab        # Vocabulary file associated with the tokenizer
```

## Training Details

Training was conducted over multiple iterations with parameters tuned for stability and efficiency:

- **Batch Size**: 16
- **Context Size**: 512
- **Embedding Size**: 384
- **Number of Layers**: 7
- **Number of Heads**: 7
- **Gradient Clipping**: Implemented to prevent exploding gradients.
- **Dropout**: Set at 5% to mitigate overfitting.

While the model managed to achieve reasonable loss values during training, the small dataset and model size posed challenges in achieving state-of-the-art performance. This emphasized the need for larger datasets and computational power for future iterations.

## Challenges Faced

- **Resource Constraints**: The model’s small size and limited dataset restricted its ability to generalize effectively. Scaling the parameters and dataset would require significantly more hardware power and time.
- **Inference Quality**: Outputs often lacked coherence, highlighting the limitations of small-scale models.
- **Optimization**: Without advanced GPU utilization techniques, there was room for improving training efficiency.

## Insights and Future Work

This project provided invaluable insights into the workings of LLMs, from data preprocessing to training and inference. Moving forward, I aim to:

- Explore advanced optimization techniques for better GPU utilization.
- Scale the model with larger parameters and datasets to improve output quality.
- Experiment with additional evaluation metrics and tasks to better understand model capabilities.

## File Details

- `wiki.txt`: Contains the raw text data for training. This file is the basis of the entire project, providing the textual content needed for tokenization and modeling.
- `wiki_tokenizer.model` and `wiki_tokenizer.vocab`: Represent the custom tokenizer for this dataset. These files allow efficient tokenization tailored to the `wiki.txt` dataset, ensuring better model performance.
- `encoded_data.pt`: Preprocessed version of the dataset after tokenization. It serves as input for the model training process, reducing preprocessing time during runtime.
- `small_llm.ipynb`: A Jupyter notebook to experiment with the tokenizer and model training pipeline. It provides an interactive environment for testing and improving the model.
- `models/latest.pt`: Checkpoint file for resuming or testing the model. This file ensures continuity in training and allows users to evaluate model performance at various stages.

## Acknowledgments

This project uses open-source tools and resources. Special thanks to the NLP and AI community for their invaluable contributions.

