---
title: "Mandelbrot and Julia - Mathematical visualization and beauty"
categories: Mathematics
author: "Vidya Bhandary"
meta: "Mathematics, Mandelbrot, Julia, Complex Numbers, Chaos"
date: 2021-1-20
---

I have been fascinated by the idea of chaos theory since I read about the butterfly effect. I read some more about it in the book 'Chaos' by James Gleick 
including about the Mandelbrot. But until I read **'Make your own Mandelbrot' by Tariq Rashid** I did not realize just how simple 
the equation to draw the Mandelbrot was.

This is the innocuous looking equation that generates the awesome Mandelbrot Set.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/Mandel_formula.PNG)

A slight change in the input to the same equation will give the Julia set. It gives rise to a complicated boundary that reveals a recursive aspect; 
there are many smaller sized Mandelbrot one can see as one zoom's in.

To learn more - look at this video - ["What's so special about the Mandelbrot Set?"](https://www.youtube.com/watch?v=FFftmWSzgmk)

So I used the code from the book (python) to get the Mandelbrot set and the Julia set. 
I also got to see the 3D surface close ups (after smoothing).

### MandelBrot 3D
![MandelBrot 3D](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/3d_mandel_1.PNG)


### Julia 3D
![Julia 3D](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/3d_julia_1.PNG)

But the fun of the Mandelbrot is when one can zoom in and see the beautiful patterns interactively.

After a bit of search (and multiple tries), I was able to finalize on JavaScript code works reasonably without needing specific 
libraries or frameworks or threads. I also improved on the color palette, to get brightly colored areas to observe the beauty of the mathematical patterns.

Following is the core of the Mandelbrot code. This calculates the value of the function for a maximum number of iterations.

### MandelBrot Code

{% gist 7711c745d83dcd9e215a40c6bc506860 %}
Ref : https://rembound.com/articles/drawing-mandelbrot-fractals-with-html5-canvas-and-javascript

### Julia Code

{% gist 6ca1e27d4adcca98020552f5b3c1a89e %}
Ref : https://rosettacode.org/wiki/Julia_set

### Color Palette Code

{% gist 691bce7f286509cb64b0bceb4383a1a4 %}
Ref : https://rosettacode.org/wiki/Julia_set

## Results

Using `mousedown` to zoom in, `ctrl` to zoom out and `shift` to pan in the Mandelbrot and Julia results, some of the images / gifs obtained are shown below.

Links to the live demo are also mentioned at the end of the post.

#### Mandelbrot gif
![Mandelbrot gif](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/MandelBrot.gif)

#### Julia gif
![Julia gif](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/Julia_800.gif)

#### Mandelbrot Image 1
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/m1.PNG)

#### Mandelbrot Image 2
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/m2.PNG)

#### Mandelbrot Image 3
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/m3.PNG)

#### Mandelbrot Image 4
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/m4.PNG)

#### Mandelbrot Image 5
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/m5.PNG)

#### Mandelbrot Image 6
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/m6.PNG)

#### Mandelbrot Image 7
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/m8.PNG)

#### Mandelbrot Image 8
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/m10.PNG)

#### Julia Image 1
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/j1.PNG)

#### Julia Image 2
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/j2.PNG)

#### Julia Image 3
![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/mandel_imgs/j3.PNG)

## Links
[Live Demo - Mandelbrot](https://mandelbrotset.netlify.app/)

[Live Demo - Julia](https://juliaset.netlify.app/)

[Full Code Mandelbrot in JS](https://github.com/vidyabhandary/mandelbrot)

[Full Code Julia in JS](https://github.com/vidyabhandary/julia)

[Python notebook with 3D images - Mandelbrot](https://github.com/vidyabhandary/mandelbrot_julia/blob/main/mandel/3d_mandel.ipynb)

[Python notebook with 3D images - Julia](https://github.com/vidyabhandary/mandelbrot_julia/blob/main/mandel/3d_julia.ipynb)

## References

1. Make your own Mandelbrot - Tariq Rashid 

  If you don't know programming or mathematics, and want to start from scratch to understand the concept behind Mandelbrot in clear, simple 
  and step-by-step manner, this book is great. Short (only ~130 pages), with plenty of illustrations, easy to grasp. 
  Its only con is that the code is in Python 2.7.

2. [HTML5 Canvas and Javascript](https://rembound.com/articles/drawing-mandelbrot-fractals-with-html5-canvas-and-javascript) -  
Main resource for the javascript code for zoom and pan function. 

3. [Color palette](https://rosettacode.org/wiki/Julia_set) - Simplest color palette code for a wide range of colors

4. [Various values of C for Julia sets](http://paulbourke.net/fractals/juliaset/)

5. [Color Inspiration](https://dev.to/foqc/mandelbrot-set-in-js-zoom-in-2hmc)

