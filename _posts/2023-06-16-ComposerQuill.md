---
title: "The Composer's Quill: Weaving Melodies using text prompts with MusicGen"
categories: GPT, AI, Text-to-music prompts
author: "Vidya Bhandary"
meta: "#AI, #GPT, #Music, #TechTrends #LLM #camenduru #PromptEngineering"
date: 2023-06-16
---

# Step by Step Guide to generate music in Google Colab

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/0-Wow1.jpg)

---

## 1. Go to https://github.com/camenduru/MusicGen-colab

### Do star his repo !!!

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/1-GithubRepo.JPG)

---

## 2. Scroll down to reach the colab notebooks

---

## 3. Choose any colab notebook and click on "Open in Colab".

### (You will need gmail ID to use colab.)

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/3-OpenInColab.JPG)

---

## 4. Loading ... This may take awhile.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/4-Loading.JPG)

---

## 5. The magical colab notebook with just 5 lines !!! Click on the arrow.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/5-ClickOnArrow.JPG)

---

## 6. You will get a warning message - Click "Run anyway".

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/6-Warning.JPG)

---

## 7. The commands in the cell will get executed - the git repo will be cloned and the required libraries will get installed This step could take a while, even with the notebook having a setting of GPU by default.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/7-CmdExec.JPG)

---

## 8. Ignore the error in red and click on the gradio live link.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/8-GradleLink.JPG)

---

## 9. The Music Generation playground !!!

### No amount of exclamations can tell how exciting it is to be able to create music with text especially for a plebian !

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/9-MusicTextPlayground.JPG)

---

## 10. Add your music prompt. This was my prompt.

**Create a binaural beat composition that promotes concentration and focus for studying. The beats should be calming and soothing, without any loud or jarring noises. Aim for a frequency range that encourages an alert mental state without inducing sleepiness.**

Add other details are per your liking

- duration of the composition
- model - melody (works with both text and sample music prompt)
- medium, small and large models (these work only with text prompts)
- an increase in temperature gives more randomness in the output

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/10-MusicPrompt.JPG)

---

## 11. Click on generate to process your text prompt to generate music.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/11-Processing.JPG)

---

## 12. The model gives the time it will take to create the music along with the number of steps and %age of completion.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/13-GenSteps.JPG)

---

## 13. Some of the other options to check out -

- Melody Condition (optional) - To remix mostly

- Music Sample - Works only with the melody model, To create music similar to a piece of music you like

- Seed gives the seed of the created music and if you want to create music similar to one you have already created before, the seed number can be added

The author of the repo says -

**These parameters, such as top-k, top-p, temperature, and classifier-free guidance, provide different ways to influence the output of a music generation model and strike a balance between creativity, diversity, coherence, and control. The specific values for these parameters can be tuned based on the desired outcome and user preferences.**

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/12-OtherOption.JPG)

---

## 14. And finally - The generated music result ! You can enjoy listening to your creation in the browser as well as download your creation to your drive as a mp4 file.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/14.JPG)

---

## 15. Trying the melody option to get a different version of the beats I like.

![](https://github.com/vidyabhandary/blog/blob/master/images/MusicGen/15.JPG?raw=true)

## 16. The result is not bad, although the original is definitely better. Lots of steps and processing when asked 40 second composition. The option with change in temperature came out pretty good.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/16.JPG)

---

## "So finally I can compose music", without knowing how to write musical notes !!

## "What a time to be alive !!!"

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/MusicGen/0-Wow2.jpg)

---

**References** :

- Tutorial by the author of the colab notebook - https://www.youtube.com/watch?v=EGfxuTy9Eeo

- One little coder - https://www.youtube.com/@1littlecoder

- In the words of Dr Károly Zsolnai-Fehér of the youtube channel "Two Minute Papers" - what a time to be alive !!!!

- The surreal images have been created using Bing Image Creator - https://www.bing.com/create
