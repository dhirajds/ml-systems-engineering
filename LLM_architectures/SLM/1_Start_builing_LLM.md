## This is majorly my attempt to understand nuts and bolts
## rather than getting into the agentic bandwagon.
## I do feel, agentic ai is transformational, 
## but i feel it works when you compare llm vs human.


## when we start comparing performance of LLM 1 vs LLM 2.
## These things like kernels, embeddings, why what will makes sense.
## I am not a noob in this field, so prespective will be helpfull for people who are like me.
## Knowing theory vs actual issues is the core attempt of this exercise.

# lets start:
# Read about transformer.
## Attention is all you need  paper by vaswani et.al.
## You should know about this.


## one major thing mentioned in the gpt paper by openai:
## They noticed that the language model they trained was able to perform tasks withot being ever trained on them.
## eg : picking the right option in the multiple choice question.

## What is pre-training vs finetuining?
## instruction finetuning vs finetuning for classification:
## instruction finetuning : give instruction then answer : use this to finetune.
## classification : spam vs non-spam of email.

## for pretraining : regular text without any labelling information.
## give it the power of predicting next token.
## for fine tuning we need labeled dataset.

## pretraining : huge amount of resources,
## finetuning : addition on the pretrained model.

