---
title: "Tokenization"
categories: GPT, LLM
author: "Vidya Bhandary"
meta: "#GPT #2024 #LLM #Tokenizer"
date: 2024-05-07
---

## 1. Learnings from Andrej Karpathy's tutorial on GPT Tokenizer

![](https://raw.githubusercontent.com/vidyabhandary/blog/868ad1cc2b3d9e91009253c7fe99fe4055708772/images/Tokenization.png)

When will I ever write a tokenizer in my life ? Probably never.

And yet Andrew Karpathy is such a phenomenal teacher that you come away with a deeper appreciation of any topic he teaches.

While his entire series on neural networks is gold standard, the one that caught my attention (yes pun intended) was the GPT Tokenizer tutorial.

Background -

What I knew of a tokernizer before this tutorial - A way to check how much to pay based the number of tokens in the input and output text. And the tokens did not match the words, they broke across words.

This tutorial opens up a whole new world of how tokenizer influences the learning of the LLM. And yes it is 'gnarly' to use Andrej's own words.

Some learnings -

1. Tokenizer for spaces in gpt2 vs latest
   Earlier in GPT-2 each space was counted separately, even if they were right next to each other. So, naturally, you'd end up with more tokens. But in the newer models, spaces next to each other were being combined.

2. By breaking down text into smaller units called tokens, tokenizers provide the groundwork for a model to generate informative embeddings.
3. An appreciation of Byte Pair Encoding (BPE), which I had never heard of before.
4. The regex from encoder.py of gpt2 yielded some new things for me.

- \p{L} - Any kind of letter from a language - I tested with Devanagari script, Kannada script.
- \p{N} - any kind of numeric in any kind of script Tested with numbers in Kannanda and Hindi.
  Having worked with mostly ASCII characters and numbers I thought this was amazing !!!

5. The basic transformer attention model is same, as is the tokenizer for other modalities, which is very impressive when you think about it. Of course this is adapted too, like Sora has visual patches.
6. Testing of chatgpt using tokens - <|endoftext|> - Your knowledge of these special tokends ends up being an attack surface potentially. He explains other types of security concerns in 1 hour introductory talk on LLMs. (Another superb talk).
7. Token economy - YAML is better than JSON.

### 8. The Best Quirk though !!! Tokens like ['SoldGoldMagikarp'](https://www.lesswrong.com/posts/aPeJE8bSo6rAFoLqg/solidgoldmagikarp-plus-prompt-generation)

Some trigger words like the one above make the gpt go haywire and behave strangely.
It is theorized that that this particular input belonged to a single reddit user, and that token was absent in the training data set for the LLM. However it was present in the tokenizer data set.
Hence -

- The token is never activated (does not learn from real data since data is not present in training data).
- Is never updated in the embedding table.
- Never sampled, never used, never trained (completely untrained).

and this feeds into the transformer and creates undefined behavior !!!

---

**Links** :

- The best introduction to LLMs imo, I personally feel this is accessible to non-tech audience too.

  [1hr Talk Intro to Large Language Models by Andrej Karpathy](https://www.youtube.com/watch?v=zjkBMFhNj_g)

- [Let's build the GPT Tokenizer](https://www.youtube.com/watch?v=zduSFxRajkE)
- [Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html)
- [Youtube Playlist - Zero to Hero](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ)
- [Cryptos tutorial - another gold standard hands-on tutorial](https://karpathy.github.io/2021/06/21/blockchain/)
- [My Github repo for NanoGPT from Andrej Karpathy's Video tutorial](https://github.com/vidyabhandary/nanogpt)
