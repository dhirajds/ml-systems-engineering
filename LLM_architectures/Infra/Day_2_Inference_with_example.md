# This is an example of memory consumption of a llm model.
# in one of the nvida blog:
# vllm paper : parameters :65 %, kv cache : 30 % memory.
# Model seving with paged attention:
# PagedAttention:
## attention algorithm



# Estimate memory consumption of llm
## https://arxiv.org/pdf/2205.05198
## https://www.youtube.com/watch?v=z2M8gKGYws4&t=550s 
## smooth quant paper.

## FYI
### what is bf16 and float 16 ?
### 1 parameter -> 2 bytes -> then 1B parameter-> 2 GB
### 1 KB is not 10^3 bytes => its 1024 bytes.
### so its almost 2GB.

### Then whatever is calculated -> actiavation values.
### 
## Inference :
### 
## Fine tuning:


## How to improve inferenece:
