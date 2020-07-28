---
title: "Self-updating GitHub profile README completely within Github"
categories: Github
author: "Vidya Bhandary"
meta: "Github, Profile, README, Github workflow"
date: 2020-07-27
---

Github's new profile readme is all the rage right now. 
### Creating a self-updating profile readme helped me -

- **Start a technical blog within Github itself**
- **Retrieve relevant information from within Github ecosystem (no separate blog)**

This self-updating readme has been inspired from the work  at 
[Building a self-updating profile README for GitHub](https://simonwillison.net/2020/Jul/10/self-updating-profile-readme/) by [Simon Willison](https://github.com/simonw). 

Following are my steps towards creating the self-updating profile readme.

### 1. Create a technical blog within Github

I used the Github Learning Lab for [GitHub Pages](https://lab.github.com/githubtraining/github-pages) to learn this. I preferred the simple look of `minima` theme with the `solarized-dark` skin.

### 2. Create a TIL repo within Github
Same approach as for creating the technical blog. Used the basic `Minimal` theme for its clean design.

### 3. Self-Updating the readme for the TIL repo using Github actions
The following files from the [repo](https://github.com/vidyabhandary/TIL) are 
needed to self-update the readme.

- `requirements.txt` *(No change required)*
- `update_readme.py` *(No change required)*
- `README.md` *(Personalize this)*
- `build_database.py` *(Personalize the url shown below)*
```python
url = "https://github.com/vidyabhandary/til/blob/master/{}".format(path)
```
- Create a manual workflow using Github actions
This will create a `./github/workflows` directory with a `main.yml` file.
Can rename this to `build.yml` or retain the existing name.
Update with code from [build.yml](https://github.com/vidyabhandary/TIL/blob/master/.github/workflows/build.yml).

### 4. Create a repo with the same name as your Github ID
This is the special repository. Its README.md will appear on your public profile!

### 5. Self-updating read-me for the Github profile.
The following files from the [repo](https://github.com/vidyabhandary/vidyabhandary) are required to
create the self-updating read-me for Github.

- `requirements.txt` *(No change required)*
- `README.md` *(Personalize this)*
- `build_readme.py` *(Personalize the urls shown below)*

```python
til_readme = "https://raw.githubusercontent.com/vidyabhandary/TIL/master/README.md"
entries = feedparser.parse("https://vidyabhandary.github.io/blog/feed.xml")["entries"]
```
- Create a manual workflow using Github actions
This will create a `./github/workflows` directory with a `main.yml` file.
Update with code from [main.yml](https://github.com/vidyabhandary/vidyabhandary/blob/master/.github/workflows/main.yml).

### And that's it !!!!
You now have a self-updating profile readme in Github that updates once a day with your 
blog posts and TILs.
