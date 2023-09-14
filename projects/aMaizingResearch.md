---
layout: project
type: project
image: img/maizePoster.png
title: "A-Maizing Research"
date: 2023
published: true
labels:
  - Undergraduate Research 
  - R Studio
  - Poster 
summary: "Phenotypic plasticity within a single maize cultivar in response to multiple abiotic stressors."
---

<div class="text-center p-4">
  <img/maizePoster.png>


B73 is known as the “standard” of maize as it has been the most widely studied cultivar and proved itself to be an important model for maize biological research. The aim of this study is to assess the response of B73 to varying environmental conditions and identify significant differences in plant growth. This helps understand how plants distribute their energy and nutrients between root and shoot systems in a specific environment, influencing plant growth. 

In our study, we employed various methods and data collection techniques. We grew the B73 maize variety in controlled environments, including drought, control, and shade conditions, within the confines of Magoon Greenhouse, allowing the plants to grow for approximately two weeks, monitoring the growth rate until the 4th leaf reached a plateau. We then concluded the measurement phase and initiated plant termination. Our data collection efforts comprised leaf analysis, involving the removal and processing of the 2nd, 3rd, and 4th leaves, which were subsequently scanned using ImageJ. This platform facilitated the measurement of surface area and various blade characteristics. We also conducted root data collection, which involved cleaning the roots and scanning them using Rhizovision to determine surface area and various root component measurements. Along with previous years data on other Maize cultivars, we used R Studio for data analysis and visualizations. 

Figure 1 displays the root-to-shoot ratio of B73 maize, revealing consistent biomass responses across treatments in Summer 2023, contrasting with the Fall 2022 control group's smaller ratios, likely due to smaller pot sizes. Letters on the graph show mean consistency determined by the Tukey test honest significant difference. Figure 2 employs a heatmap and confusion matrix to evaluate growth rate variations across environments using machine learning algorithms like Random Forest and Support Vector Machine (SVM) for classification and regression, which shows us how likely each year of B73 growth rate is to be confused with eachother.

In this project we have successfully analyzed the response of a specific maize cultivar to various environmental conditions. The accuracy of our predictions for these differences was remarkably high. Furthermore, we observed substantial phenotypic variation within B73 cultivar through qualitative and quantitative characteristics that shows us what environment the B73 maize was grown in. This valuable data on the growth patterns of B73, known as the "standard" maize variety, in diverse environments will serve as a reference for future comparisons with other maize cultivars.



Here is some code that illustrates how we read values from the line sensors:

```cpp
byte ADCRead(byte ch)
{
    word value;
    ADC1SC1 = ch;
    while (ADC1SC1_COCO != 1)
    {   // wait until ADC conversion is completed   
    }
    return ADC1RL;  // lower 8-bit value out of 10-bit data from the ADC
}
```

You can learn more at the [UH Micromouse News Announcement](https://manoa.hawaii.edu/news/article.php?aId=2857).
