* disclaimer: Its my blog for my learning, not to showcase as a article.
* but if I do something for personal use and someone else can get some benefit out of it, #nothingbetterthanthat.

# In this log, I capture my learning about inference memory requirement.
## What I indend to learn.
### How much memory is required/ minimum requiremnts?
### Challenges with scaling ?
### How memory is utilized ?
### How to optimize memory usage?



## Why are we talking about memory and not about prompt ?
### 1.These things are not a concern, when you blindly use hosted api.
### 2.Memory requirement is x, and you have 2x at disposal.
### This matters when you want to get that last bit of performance, from the available resource.


 -> GPU out-of-memory errors
 -> Inability to increase batch size
 -> Sudden latency spikes with long prompts
 -> Low GPU utilization despite high demand

## lets start with what is memory requirement ?
### lets start with decoder-only transformer.
#### Model weights:
##### Basically, what we call as a model...like that 7B parameters
##### Independent of batch size and sequence length.

#### Activations:
##### Created during each forward pass
##### Freed layer-by-layer
##### Scale with batch size and hidden size
##### Not required later, so do not accumulate over time.

#### KV Cache
##### Avoid repeated calculation of same things.
##### Grows linearly with sequence length : More things to save.
##### Grows linearly with batch size : as expected
##### Persists for the lifetime of the request : You need all the K,V for next token prediction.
##### Must stay on GPU to avoid severe latency penalties

## What i feel is:

### Inference compute scales with tokens generated.
### Inference memory scales with tokens seen.
These are not the same thing.
  A request that generates 10 tokens after a 4k prompt: Does little compute
  Consumes a large, persistent KV cache almost propotional to those 4k token prompt size.
  Batching amplifies this effect:
Compute benefits from batching : utilization increases
Memory cost multiplies with batching : Where will you save those KV for each batch .that too in memory.
This creates a hard ceiling that cannot be optimized away with better kernels.


several constraints already:
Increasing context length directly reduces maximum batch size:
Increasing batch size directly reduces maximum context length-> think about it.(dont try to prove wrong. just think)
Throughput tuning is primarily a memory budgeting exercise.
GPU utilization numbers are misleading without memory context.


## Questions:
### Are multiple copies of model weights loaded when batch_size increases?
### Why do models have limitations on context window, Can we make it work even if we exceed.
### Without caring much about performance.


