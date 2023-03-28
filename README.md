# ParaLLaMA
Run large LLaMA with long context length with tensor parallelization support applied to the HF implementation of LLaMA. Using this port, I'm able to run LLaMA 13B with up to 2048 context length split across 4 16GB GPUs. 

## Installation

Create a new python environment and then run ```pip install -r requirements.txt```. No need to install any different branch of the transformers library, all LLaMA class definitions are contained in this repo. 

## Demo

Run ```python parallelization_example.py``` in conda with the appropriate model and prompt to see it in action! Refer to the ```inference_example.py``` and ```training_example.py``` for single-GPU / CPU demonstrations. 

Note, parallelformers requires each parallelize call to be wrapped in a ``if __name__ == "__main__":`` block. Additionally, parallelformers only supports inference, not training. 

**Credits:** Significant portions of the codebase are ported from the [PR](https://github.com/huggingface/transformers/pull/21955) by [Jason Phang](https://github.com/zphang). Inference and training examples are from [user-friendly LLaMA repo](https://github.com/ypeleg/llama) from [Yam Peleg](https://github.com/ypeleg). 
