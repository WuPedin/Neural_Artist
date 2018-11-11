# Neural_Artist
Use neural network to do style transformation.

(These files are review of Deep Learning Bootcamp of 木刻思.)

Implement [A Neural Algorithm of Artistic Style](https://arxiv.org/pdf/1508.06576.pdf).

----------------------------------------------------------------------

## Goal
- To apply style transformation to content image.

## Preparation
- content image
- style image
- VGG19 or other pretrained model for feature extraction

## Basic Concept
- Use VGG19 to extract features. It is believed that shallow layers represent style-relative features and deep layers represent content-relative features.
- We want our output image to be both similar to content image and style image. Therefore, we calculate two losses:

  ![image](https://github.com/WuPedin/Neural_Artist/blob/master/Loss_content.PNG)

  which mean difference between output image and content image after feature extraction.

  ![image](https://github.com/WuPedin/Neural_Artist/blob/master/Loss_style.PNG)

  which mean difference between output image and style image after feature extraction. 

- And then use total loss to backpropagate:

  ![image](https://github.com/WuPedin/Neural_Artist/blob/master/Loss.PNG)
  
  alpha and beta are used to adjust the output image.

## Result
- The higher alpha/beta, the more impact that content influence output and vice versa.
- The deeper layers used for feature extraction, more detail we can found in output image.
  ![image](https://github.com/WuPedin/Neural_Artist/blob/master/Result.PNG)



