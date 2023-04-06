# logoNet

## 1. logo sketch dataset

We have collected an instance-level logo sketch dataset, which contains a total of 2,000 logo instances. We have also collected three or more corresponding sketches
for each logo to capture the variability of painting ability and style, leading to a total of 9,347 sketches. In addition, we also provide 2,000 text labels for each
instance, such that the dataset allows cross-modal retrieval. The following table compares our newly collected logo sketch dataset with the other existing sketch datasets.
To our knowledge, our collected dataset is the first instance-level logo sketch dataset which lends itself to fine-grained and cross-model logo sketch retrieval.

![QQ20230406210632](https://user-images.githubusercontent.com/87791730/230387882-04e8e150-b2ae-4ce9-ae29-d417c20a6f7e.png)


These 2,000 logo images come from all walks of life and can be divided into three categories : transportation, life services, and enterprises business, which meet 
the needs of daily life scenes. The following image is the classification information of the logo images.

![fenlei](https://user-images.githubusercontent.com/87791730/230397642-b37bbdc8-426b-4546-bd8e-86fa06609d5e.png)



Since our dataset is built for instance-level retrieval, the logos should cover instance-level variability of visual appearance. To this end, we have exhausted major 
websites to collect logos in daily life scenes. Since a logo sketch does not contain color information, logos with the same shape but different colors are filtered out, 
and duplicate logos are removed with only one remained. Thus, a total of 2,000 logo images are obtained.

In terms of the sketch collection, we employ the collected logo images to generate corresponding sketches. To reflect the real-world application scenarios along with 
the variability of painting ability and style, we use different input devices to collect sketches and generate multiple sketches for each logo image. Considering 
the diversity of sketch painting, the volunteers collecting the logo sketches are divided into three groups. The first group of volunteers have professional 
drawing ability and they drew sketches on a tablet PC. With general painting ability, the second group of volunteers make use a variety of equipment including
mobile phones, white paper and drawing boards to draw sketches. Lacking sufficient drawing skills, the third group of volunteers draw incomplete or simple strokes 
of logo sketches using different input devices.Given a logo, multiple corresponding sketches need to be painted and collected. For a given logo instance, three or 
more sketches are obtained by different volunteers under different settings, leading to a total of 9,347 sketches.Some representative logo examples and the 
corresponding sketches drawn are shown in the following figure.

![111](https://user-images.githubusercontent.com/87791730/230397710-28b7f903-2817-4eee-a911-5797a698f5cc.png)


The logo sketches exhibiting diverse drawing qualities under different settings indicate different difficulty levels of sketch retrieval, and we divide the whole 
sketch dataset into easy, medium and hard three subsets accordingly.The following figure is an example of easy\medium\hard subsets.

![emh](https://user-images.githubusercontent.com/87791730/230388671-8dc339f0-9e70-40b6-8591-3ccc95a783db.png)




In addition to sketch-photo paired labels, we also collect 2,000 text annotations as auxiliary information for sketches, allowing cross-modal logo sketch retrieval.
The labeled texts mainly characterize the key attributes of logos in terms of color,shape, quantity to supplement the logo description. They not only reduce the
requirements for human sketch painting ability but also improves the retrieval accuracy of the model.

![biaozhu ](https://user-images.githubusercontent.com/87791730/230388234-ab7afc94-76a8-42a6-9f6e-fec364beba07.png)




## 2. instance-level logo sketch retrieval model

We develop a triple-branch network based on hybrid attention mechanism termed logoNet for fine-grained logo sketch retrieval. The following figure illustrates
the overall framework of LogoNet. In the triple-branch network, large-kernel convolutions are followed by CNN backbone with hybrid attention mechanism embedded.

![20230406212507](https://user-images.githubusercontent.com/87791730/230392004-bb5ac14e-5bb9-4ef1-9b54-f6fe1be11023.png)



The model can distinguish visually similar trademark images, which can not only capture the overall features of the image, but also capture fine-grained features. 
On the hard class, the model can also retrieve the corresponding positive samples with very few abstract strokes in the logo sketch, indicating that for 
logos that are obscured in life or blurred in memory, users can still enter incomplete sketches or simple strokes into the model, and the model can still 
retrieve the corresponding logo image from the library.

![image](https://user-images.githubusercontent.com/87791730/230392041-eb7d955a-fde3-45e0-8dca-c93f6c89b628.png)



The following figure shows the visual results of cross-modal retrieval on our dataset. Obviously, if there is color information in the added text label, the model 
tends to output the logo image of that color.

![image](https://user-images.githubusercontent.com/87791730/230392082-999f5010-94c9-4eb6-982f-5c9ad71bc675.png)


## Citations

@articles{logoNet2023,

title={LogoNet: a fine-grained network for instance-level logo sketch retrieval},

author={Binbin Feng, Jun Li, Jianhua Xu},

journal={arXiv perprint arXiv:4827887, 2023.},

year={2023}

}

## The file VGG_logo_model_best.pth above is our trained model.

