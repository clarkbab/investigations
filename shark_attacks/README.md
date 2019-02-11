# Shark Attacks

This investigation was carried out using data from the [Global Shark Attack File](http://www.sharkattackfile.net). This data was compiled by a global team of researchers and published online. A larger dataset is available for 'serious researchers'.

This repo contains the `Shark Attacks` Jupyter notebook in which all investigation was carried out.

## Tools

Third party libraries used for this project include:

* [geopy](https://geopy.readthedocs.io). "geopy is a Python 2 and 3 client for several popular geocoding web services." We use this to search for the geographical co-ordinates of locations for mapping.
* [folium](https://github.com/python-visualization/folium). Folium is a python visualisation library. This is used to build the world map.
* numpy, pandas, sklearn, matplotlib, seaborn 

## Research Questions

1. What proportion of shark attacks are fatal for the human/s involved?
2. Can fatality be predicted?
3. How are attacks distributed globally?

## Outcomes

**1. What proportion of shark attacks are fatal for the human/s involved?**

Globally, it seems that only ~25% of shark attacks are fatal for the human involved. When we split the data by various other conditions, we see those variables that increase and decrease this likelihood. For example, when we split by Species, we see that there are certain species for which the percentage of fatal attacks is higher (e.g. the Tiger shark at ~28%) and there are those with very low likelihood of fatality (e.g. the Wobbegong shark with 0%).

**2. Can fatality be predicted?**

After fitting a LogisticRegression model to the dataset, we were able to obtain an accuracy of **81.28%**.

**Classification Report**

| Class            | Support | Precision | Recall | F1 Score | 
|------------------|---------|-----------|--------|----------|
| Y                | 387     | 0.61      | 0.47   | 0.53     |
| N                | 1333    | 0.86      | 0.91   | 0.88     |
| Weighted Average | 1720    | 0.80      | 0.80   | 0.80     |

We can see from the classification report that we were better at predicting the N outcome than the Y outcome. We did have a smaller sample size for the Y case so this could be an explanation for the failings of our model.

**3. How are attacks distributed globally?**

In the interests of getting some experience with more advanced plots, the folium library was used to plot the locations of shark attacks globally. This clearly shows the clustering around Florida, South Africa and parts of Australia amongst others.

**Shark Attack Global Distribution** 

![What?](https://github.com/clarkbab/investigations/blob/master/shark_attacks/map.png?raw=true)