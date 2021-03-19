# painting-recovery
## This code was made in collaboration with Riley Groeschel, Alexander Klein, and Sam Horrigan for Image Processing and Visualization class. 
Team SARA: Homework 1 Code Explanation
Our code uses the ground truth images in Figure 1, and the AI-generated images in Figure 2 and finds the 2D Fourier Transform of each. It then divides each AI-generated image’s Fourier transform by the corresponding ground truth image’s Fourier transform, to determine the “stroke” filter for each. It then finds the average of the four filters, and that is the filter that we use to predict what the original image looked like along with some color and sharpness enhancements.
Figure 1: Ground truth images

Figure 2: AI-generated images in Cezanne’s style

	To predict what the original image looked like, we take the Fourier transform of a painting by Cezanne, divide that by the filter, and then take the inverse Fourier transform of that to get the output image. The result from just the Fourier transform is rather blurry and not aesthetic as a real image. Therefore, saturation is increased by 50% and brightness by 5%, which were determined to be the best combination by manipulating all 4 FFT outputs to the ground truth images in ImageJ. Finally, a sharpening mask was applied that focused on three areas: strong sharpening at the high threshold areas, slight blurring at the low threshold areas, and moderate sharpening in the middle. In Figure 3, the input images were the AI-generated images from Figure 2 after our filter was applied.

Figure 3: Recovered images



	This process can be performed on other paintings by Cezanne as well; in Figure 4, you can see a painting of a city in France, and a prediction of what Cezanne’s original view of the city looked like. Because this painting is in a bit more of an impressionistic style than the AI-generated images above, the final result is splotchy and there is not as much fine detail as in the predictions in Figure 3.





Figure 4: Ground truth painting and recovered image


Figure 5: Ground truth painting and recovered image


The recovered images are a good approximation of the ground truth images, but they are not identical. The reason for this is that the paintings do not contain enough detail in comparison to the ground truth  for us to get the perfect recovered image, repeated features in the painting may have caused striping in our recovered image, and we have no phase information. 
