Task:

We investigate how a small instruction-tuned language model answers questions from TruthfulQA (a benchmark of questions that many people answer wrongly) across categories such as misconceptions, conspiracy theories, superstitions, paranormal etc.

Phase I: we create a new dataset by reframing each question–answer pair with fixed templates: neutral (“Is this answer correct?”), leading (“I’m pretty sure the answer is…, right?”), false authority (“My teacher said…”) and doubt. We visualize how the model’s yes/no confidence and correctness shift with framing and category, to find out when wording pushes the model into agreeing with a wrong answer or giving up a correct one.

Phase II: we look inside the model, at the hidden states of each layer, to check whether it still internally represents the correct answer when the framing makes it answer wrongly (e.g. with probing, following Marks & Tegmark, 2023, and the logit lens).

Dataset: https://huggingface.co/datasets/truthfulqa/truthful_qa

Model: 

We use Qwen2.5-1.5B-Instruct, a pretrained multilingual language model that can translate between different languages, answer questions, and follow instructions. We will compare its responses to the original questions and differently framed versions to investigate how wording affects its answers.

Model link: https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct
