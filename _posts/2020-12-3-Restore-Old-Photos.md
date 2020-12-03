---
title: "Step-by-Step guide to restore old photos"
categories: Image AI, Deep Learning
author: "Vidya Bhandary"
meta: "Image AI, Deep Learning"
date: 2020-12-03
---

A few months back, Microsoft shared code for **[old photo restoration](https://github.com/microsoft/Bringing-Old-Photos-Back-to-Life)**. The implementation was in pytorch. 

I tried to use the code to restore some old damaged snaps. I found that not all old photos can be enhanced. Reasonably well defined blemishes and lines are handled well but diffused areas of damage don't fare that as good.
Nevertheless it is a very impressive photo restoration using AI.

### This is a step-by-step guide to using the code to restore your old photos using Google colab.

You need - 
- Gmail ID to run the colab notebook
- Old photo (≤500 x 500 pixels only)

## 1. Copy the colab notebook 
Save the **[colab notebook](https://colab.research.google.com/drive/1NEm6AsybIiC5TwTU_4DqDkQO0nFRB-uA?usp=sharing#scrollTo=LMnje_NWj24x)** at this link to your own gdrive so that you can use this notebook in your google colab environment.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i0_Save.png)

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i1_Save_Copy_In_Drive.png)

## 2. Change the run time environment

Change the runtime type to Python3 and the hardware accelerator to GPU as mentioned at the top of the notebook.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i2_GPU_Runtime_1.png)

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i2_GPU_Runtime_2.png)

## 3. Run the notebook cells

Run all the cells till the section **'Try it on your own photos'**. So all steps under *'Git Clone', 'Set up the environment', 'Run the code'* need to be completed.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i4_Run_Till_Here.png)

## 4. Upload the files to be restored

When you run the cell after the heading **'Try it on your own photos!'** you will see a button to **'Choose files'**. You can choose multiple files or a single file.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i5_Choose_files.png)

## 5. With scratch or Without scratch flag

After the files are uploaded in the next cell - choose the restoration type. If the photos have scratches then simply add the flag `--with-scratch` at the end of the python code. Otherwise no change to be made.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i6_Choose_scratch_flag.png)

## 6. Results display

After this cell completes its run, the result is displayed side by side with the original input picture.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i7_Result_Photo_side_by_side.png)

## 7. Download the results

Run the next cell which copies the output to a zip file and downloads this zip file. This downloaded file will contain the resultant **restored image(s).**

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i8_download_res.png)

## 8. Issues

### a. Scaling images

If you upload a file that is more than 500x500 pixels - the large image is skipped and not processed.

![](https://raw.githubusercontent.com/vidyabhandary/blog/master/images/i9_Error_Big_Image.png)

You can scale images in **[GIMP](https://docs.gimp.org/2.6/en/gimp-tutorial-quickie-scale.html)** or use any image editor tool to ensure it is within the limit prescribed.

### b. Incognito Mode

If you run the colab notebook in Incognito mode you may come across this error message.

**`Upload widget is only available when the cell has been executed in the current browser session. Please rerun this cell to enable.`**

To overcome this - you can either run the notebook in regular chrome window or use whitelist cookies from google like this -

**`https://[*.]googleusercontent.com:443`**

For more details - check out this [stackoverflow](https://stackoverflow.com/questions/48420759/upload-local-files-using-google-colab/48427329) link.

---

References:
- [Github - Microsoft/Bringing-Old-Photos-Back-To-Life](https://github.com/microsoft/Bringing-Old-Photos-Back-to-Life)
- [Bringing Old Photos Back To Life](http://raywzy.com/Old_Photo/)
- [Bringing Old Photos Back To Life Tutorial](https://www.youtube.com/watch?v=mS-LSjQqh4A)

