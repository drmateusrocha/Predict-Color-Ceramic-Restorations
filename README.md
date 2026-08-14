# Capstone-Project
Rocha's Capstone Project - Berkeley

## AI/ML models to predict the final color of leucite-reinforced ceramic veneer restorations

**Mateus Rocha**
Center for Dental Biomaterials, College of Dentistry of University of Florida.
mrocha@dental.ufl.edu
www.biomaterials.dental.ufl.edu

## Executive summary

This is Capstone Project to complete the requirements for the Certificate in AI/ML at UC Berkeley. 

The study aims to develop an algorithm that can eliminate the necessity of visual inspection for shade selection and shade matching of any esthetic and restorative procedure using glass-based ceramic restorations. Recently, the Ivoclar Vivadent e.max shade navigation app was a considerable advance in the field to assist dentists in selecting the appropriate ceramic shade, translucence, and thickness. Still, there are several limitations as the app relies on the dentist's color perceptibility and acceptability. This study shows the algorithm developed and clinical spectrophotometric analysis aid using artificial intelligence to assist the dentist in selecting shade, type, thickness, and translucency of the ceramic restorations. 


## Rationale

Dental ceramics are in constant development and they are an essential material for restorative dental treatments. For conventional feldspathic ceramics, the dental technician constructs a ceramic restoration by condensation and sintering of layers of ceramic powder with different shades and opacities to mimic the natural tooth structure.2,3 However, this approach is becoming obsolete since computer-aid design and computer-aid manufacturing (CAD/CAM) can produce monolithic ceramic restorations with similar optical properties but higher mechanical strength.
IPS Empress® CAD (Ivoclar ­Vivadent, Schaan, Liechtenstein) is a leucite-reinforced ceramic that presents a higher leucite volume as its crystalline phase, resulting in improved mechanical properties. The material is processed utilizing the hot-pressing technique or the CAD/CAM technique. The mechanical strength combined with excellent optical properties makes leucite-reinforced ceramics suitable for veneers and anterior crowns.
The chairside CAD/CAM dentistry is an extraordinary achievement that brings the dentist the opportunity for selecting and handling the ceramic materials. Consequently, the final results depend on the dentist skills with these particular materials. Considerable research attention has been devoted to color matching of CAD/CAM ceramic materials. However, the majority of the laboratory studies are hard to clinically translate due to the vast number of clinical variables
Shade guide is the traditional and most common method used for shade evaluation in dentistry but still presents many limitations. Instrumental color measurement has increased in popularity over the years. Different types of spectrophotometers, colorimeters, and imaging systems have been used in dentistry for shade evaluation.
Instrumental measurement provides objective and quantitative data, which reduces the subjectivity of the visual method. However, there is no method to combine the CIELab coordinates (L*, a* and b*) obtained from the tooth substrate and ceramic to predict the best ceramic type, shade, and thickness. The understanding of these interactions would extend the use of spectrophotometers in dentistry and it can lead to development of an algorithm for spectrophotometric software-assisted shade selection.

## Research Question
Which regression model is the most accurate in the test data set, using their default parameters?

### Specific aims and hypotheses
The specific aims of the study are: 1 - Evaluate the L*, a* and b* of monolithic ceramics with different thicknesses, shades, and translucencies, cemented on white, black, A1, and A3 substrates with translucent resin cement. 2 - Create an algorithm based on the regression analysis of the color coordinate parameters (L*, a* and b*) to predict the final color of the ceramic restoration and the color change (ΔE00) from the initial substrate color. The hypotheses tested in this study are: H1 - There are significant differences in the L*, a* and b* color coordinates of monolithic ceramics with different thicknesses, shades, and translucencies cemented on white, black, A1, and A3 substrates with translucent resin cement. H2 - The algorithm created using the color coordinate parameters (L*, a* and b*) predicts the final color of the ceramic restoration and the color change (ΔE00) from the initial substrate color.


## Data Sources
The data source can be found in this GitHub depository. The data collection was obtained by the author research group according to the following protocol:

Leucite-reinforced glass-ceramics blocks (IPS Empress® CAD, C14, Ivoclar Vivadent, Schaan Liechtenstein) (Figure 1) in 4 different shades (HT - A1, A3; LT - A1, A3) were used in this study. The blocks were bonded to dressing sticks (Buehler®, Lake Bluff, IL) to allow precise cuts without chipping of the specimens during the section. The assembly was mounted in a precision diamond saw machine (Isomet, Buehler®, Lake Bluff, IL with the Buehler's® Isomet diamond blade 15 LC, dimensions: four inches (102 mm), thickness: 0.012 in (0.3 mm) Buehler®, Lake Bluff, IL) and the blocks were sectioned under water cooling at 400 rpm. Specimens (n = 5) perpendicular to the long axis of the block were obtained with thicknesses of 0.3, 0.5, 0.7 and 1.2 mm. The accuracy of the final thickness was determined with a digital caliper (Mitutoyo Corp®, Kawasaki, Japan) with an accuracy of ± 0.05 mm. The glaze was not applied to avoid high reflection luster that could affect shade measurement. A pilot study showed that samples prepared following this protocol present similar superficial rugosity to the samples milled in the CEREC® MC XL milling machine (according to the ISO 25178 - Geometric Product Specifications – Surface texture, Sa = 18.56 ± 1.7 µm for the Isomet 15LC Diamond Saw and Sa = 17.57 ± 1.8 µm for the CEREC® MCXL milling machine, p = 0.832).
An experimental translucent resin-based cement with a refractive index of 1.5229 and without photoinitiators was produced to simulate the cementation of the ceramic veneer on the substrate. This simulation mimicked the refractive index changes and the light propagation through the interfaces between the ceramic-cement and cement substrate. 
Four different substrates were used: white background; black background; IPS Empress® LT A1 CAD/CAM block; IPS Empress® LT A3 CAD/CAM block. For reference, the CIELab coordinates of backgrounds were black (L*= 22.06, a*= 0.33, b*= 0.30), white (L*= 97.29, a*= -0.06, b*= 2.39), IPS Empress® LT A1 (L*= 71.29, a*= 0.99, b*= 10.87), and IPS Empress® LT A3 (L*= 64.30, a*= 2.13, b*= 14.82).

The color parameters of each specimen were obtained with a D65 illuminant over the different backgrounds interposed with the translucent resin cement using a calibrated spectrophotometer (CM-700d, Konica Minolta®, Tokyo, Japan) with a target mask with a sensor-opening diameter of 3 mm (SAV). The CIE 1931 2° Standard Colorimetric Observer was used to calculate color coordinate values for each specimen. The sensor opening of the spectrophotometer was placed in the center of each specimen and three measurements were collected in both SCI (specular component included) and SCE (specular component excluded) modes. The CIELab coordinates (L*, a* and b*) from the specimens were used to evaluate color change (ΔE00) from the substrate to the surface of the veneer according to the CIEDE2000 formula: ∆E00 = [(∆L/KL.SL)2 + (∆C/KC.SC)2 + (∆H/KH.SH)2 + RT.( ∆C/KC.SC).( ∆H/KH.SH)]0.5 , where ΔL, ΔC and ΔH are the differences in lightness, chroma and hue, and Rt is a function (the so-called rotation function) that accounts for the interaction between chroma and hue differences in the blue region. Weighting functions, SL, SC, and SH adjust the total color difference for variation in the location of the color difference pair in L*, a* and b* coordinates, and the parametric factors KL, KC, and KH are correction terms for the experimental conditions, which were set to 1. Differences in each inherent color parameter were also determined as ΔL*, Δa*, and Δb* by subtracting each specimen from the substrate color coordinate parameter value (+a* = red, −a* = green; +b* = yellow, −b* = blue; +L* = white, -L* = black).

The data set containing all variable were organized into:

    #Final CIELAB Result
    Lfinal = L* value of the final restoration; 
    afinal = a* value of the final restoration; 
    bfinal = b* value of the final restoration; 
    
    #Substrate Parameters
    Lsub= L* value of the substrate; 
    asub = a* value of the substrate; 
    bsub = b* value of the substrate;
    
    #Ceramic Parameters
    Lcer= L* value of the ceramic block; 
    acer = a* value of the ceramic block; 
    bcer = b* value of the ceramic block; 
    T = thickness of the ceramic restoration; 
    

## Methodology
I am using the Jupyter Notebooks with scikit-learn libraries. 

First I attempted different Regression Models using their default parameters

The models tested were:
    
    BaggingRegressor()
    CCA()
    DecisionTreeRegressor()
    DummyRegressor()
    ElasticNet()
    ExtraTreeRegressor()
    ExtraTreesRegressor()
    GaussianProcessRegressor()
    KNeighborsRegressor()
    KernelRidge()
    Lars()
    Lasso()
    LassoLars()
    LinearRegression()
    MLPRegressor()
    MultiTaskElasticNet()
    MultiTaskElasticNetCV()
    MultiTaskLasso()
    MultiTaskLassoCV()
    OrthogonalMatchingPursuit()
    PLSCanonical()
    PLSRegression()
    RANSACRegressor()
    RadiusNeighborsRegressor()
    RandomForestRegressor()
    Ridge()
    RidgeCV(alphas=array([ 0.1,  1. , 10. ]))
    TransformedTargetRegressor()

The DecisionTreeRegressor() was the best model with the lowest mean absolute error (MAE, 0.226) ad the highest R2 score (0.99)

Thus, it was decided to fine-tune the hyperparameters of the Decision Tree Regressor and the best hyperameters were {'criterion': 'friedman_mse', 'max_depth': 28, 'min_samples_leaf': 1}

The feature importance shows:

  Thickness  Lsub  asub  bsub  Lcer  acer  bcer
0      0.124 0.597 0.237 0.013 0.012 0.011 0.006

<<<<<<< HEAD
## Results

### Exploratory Analysis (Notebook 1)

The complete notebook for exploratory analysis can be found here : 

- Notebook 1 > https://github.com/drmateusrocha/Capstone-Project/blob/dfc4545826616367db78551fd92b00cc0de4b790/notebooks/Notebook%201%20-%20Exploratory%20Analysis.ipynb

The Figure 1 above  shows the CIELab values for the substrates and ceramics blocks used in this study. For the L* value, it can be noticed that the Black background had the lowest L* value as the White background had the higher L* value. The A1 shade had higher L* values than the A3 shade for the ceramic blocks, regardless of the translucency (LT or HT). For the same shade color (A1 or A3), the LT ceramics had higher L* values than the HT ceramics. For the a* values, it can be noticed that the ceramic block IPS Empress® HT A1 has a negative a* value, which makes it with a greenish aspect. The White background has also a negative a* value, but it is very close to 0. The black background has a positive a* value, which makes it with a reddish aspect. The ceramic IPS Empress® LT A3 has the highest a* value followed by IPS Empress® HT A3 and IPS Empress® LT A1, respectively.
For the b* values, all substrates have a positive b* value. The White background has a higher b* value than the black background. The ceramic A3 have higher b* value than the ceramic A1. The ceramics LT have a higher b* value than the ceramics HT.


Figure 1 > Substrates




#### Analysis of Variance

Figures 3, 4, 5 and 6 show the L*, a*, b* and ΔE00 values of the different ceramic restorations with different thickness cemented on the different substrates. For the L* values (Figure 3), significant differences were found among all variables (substrate vs ceramic type vs thickness, df = 27, F = 54.87, p < 0.001). According to the pairwise comparison, for the same ceramic type and thickness, the differences were found for all substrate shades (df = 3, F = 5.1x105, p < 0.001), where the L* final of the restoration follows White > A1 > A3 > Black for the different background.
Within the same background, the influence of the different ceramic shade and ceramic thickness is statistically significant (df = 9, F = 208.19, p < 0.001). However, when the pairwise comparison is performed the color of the background and the color of the ceramic dictates if the L* of the final restorations is going to be higher or lower than the background. For the white background using the different ceramics, as thinner the ceramic thickness higher is the L* of the final restoration. And the inverse is true for the Black background, as thinner the ceramic thickness lower is the L* of the final restorations. For the A1 and A3 backgrounds, the influence of the thickness on the L* of the final restoration depends on the difference of the L* values of the ceramic restoration and the background. For A1 and A3 backgrounds, restored with IPS Empress® LT A1 and IPS Empress® LT A3, respectively, no differences were found in the L* of the final restoration among all different thicknesses.
The same pattern was founded for the a* and b* values. However, it is important to notice that the L*, a* and b* values will influence the final color independently, but an alteration of the axis (L*, a* or b*) can significantly influence the ΔE00fs and subsequently the final color of the restoration.


Fig L by ceramic
![alt text](https://github.com/drmateusrocha/Capstone-Project/blob/8b77156b7e4899b83990cce20da017619bb41c70/images/fig1-L_by_ceramic.jpeg)

Fig


#### Correlations

For the Lf variable, the Pearson’s correlation analysis found a significant linear interaction with the bf (r = 0.779, p < 0.05), Ls (r = 0.936, p < 0.05), Δafs (r = 0.701, p < 0.05), Δbfs (r = 0.716, p < 0.05) and ΔLsc (r = 0.918, p < 0.05). These variables were submitted to multivariate linear regression analysis and the results shows an Adjusted-R2 of 0.980 (Figure 7). All variables were statistically significant (p < 0.001) for the model fitting. The regression function generate was f(Lf) = - 0.179 bf + 0.812 Ls – 9.406 Δafs + 1.357 Δbfs + 0.245 Δbfc – 0.289 ΔLsc + 15.42.

For the af variable, the Pearson’s correlation analysis found a significant linear interaction with the bf (r = 0.897, p < 0.05), Ls (r = 0.732, p< 0.05), ΔLfs (r = - 0.854, p < 0.05), Δbfc (r = 0.825, p < 0.05), ΔLsc (r = 0.744, p < 0.05) and ΔE00sc (r = - 0.752, p < 0.05). These variables were submitted to multivariate linear regression analysis. All variables were statistically significant (p < 0.001) for the model fitting, with exception of ΔE00sc (p = 0.086) that was exclude from the model. The results of the regression analysis show an Adjusted-R2 of 0.952 (Figure 8).  The regression function generate was f(af) = 0.136 bf - 0.029 Ls – 0.077 ΔLfs + 0.037 Δbfc – 0.021 ΔLsc + 1.83. 

For the bf variable, the Pearson’s correlation analysis found a significant linear interaction with the Lf (r = 0.779, p < 0.05), af (r = 0.897, p < 0.05), Ls (r = 0.891, p < 0.05), ΔLfs (r = - 0.896, p < 0.05), Δafs (r = 0.839, p < 0.05), ΔLfc (r = 0.804, p < 0.05), and ΔLsc (r = 0.899, p < 0.05). These variables were submitted to multivariate linear regression analysis. All variables were statistically significant (p < 0.001) for the model fitting, with exception of ΔLfc (p = 0.551) and ΔLsc (p = 0.562) that were exclude from the model. The results of the regression analysis show an Adjusted-R2 of 0.962 (Figure 9).  The regression function generate was f(bf) = 366.80 Lf + 6.743 af – 366.549 Ls – 366.424 ΔLfs – 0.978, Δafs - 13.717. 

No linear relationship was found for the thickness variable; thus, several different non-linear models were applied. It was found that the thickness is influence by the sigmoid function of the variable ΔE00sc (Adjusted-R2 = 0.915, p = 0.014) (Figure 10). The function to predict the thickness of the ceramic follows: T(x) = 1 / 1 + 1.16 (ΔE00sc)-0.047.

The excel spreadsheet with algorithm GUI can be download in the supplementary material. Figure 11 shows a step-by-step example on how to use the spreadsheet. In this example, an acceptability threshold of 1.77 was used for the calculations (Figure 11-A). The L*, a* and b* of the substrate, Empress® LT A3 ceramic, was inserted (Figure 11-B).  The L*, a* and b* of the target color, Empress® LT A1 ceramic, was inserted (Figure 11-C). These L*, a* and b* values can be clinically measured using the spectrophotometer or the dentist can use the algorithm “Ceramic Data Base” tab to select the L*, a* and b* values by means of shade selection by visual inspection.  The outcome of this algorithm application example shows that to achieve a target shade A1 using Empress® ceramic veneer on a substrate A3, the minimum ceramic thickness is 0.8.


### Multivariate Regression (Notebook 2)

The complete notebook for multivariate regression can be found here : - Notebook 2 > https://github.com/drmateusrocha/Capstone-Project/blob/dfc4545826616367db78551fd92b00cc0de4b790/notebooks/Notebook%202%20-%20Multivariate%20Regression%20Models%20for%20the%20Color%20Variables.ipynb

The DecisionTreeRegressor() was the best model with the lowest mean absolute error (MAE, 0.226) ad the highest R2 score (0.99)

Thus, it was decided to fine-tune the hyperparameters of the Decision Tree Regressor and the best hyperameters were {'criterion': 'friedman_mse', 'max_depth': 16, 'min_samples_leaf': 1}

The feature importance shows:
    
    Thickness = 0.125
    Lsub = 0.591
    asub = 0.007
    bsub = 0.248
    Lcer = 0.011
    acer = 0.014
    bcer = 0.004   

Thus, according to this model the most important features to predict the L, a and b final are the Lsub, the bsub and the thickness.

The model was deployed using the API Gradio for simple GUI.


### Simple Neural Network (Notebook 3)

The complete notebook for the Simple Neural Network can be found here: - Notebook 3 > 

This model was developed using TensorFlow and GridSearchCV (Scikit Learn) for optimization.

First the a simple neural network (NN) with 7 inputs, 2 hidden layers, 5 neurons per layer and 3 outputs was attempted. The MAE error for this NN was 1.864.

Then, a GridSearchCV optimization was done to determine the number of hidden layers (1 or 2) and the number of neurons per hidden layer (20, 10, 5, 3) using batch sizes of 20, 50, 100 and epochs of 20, 50, 100.


The MAE error for the optimized NN was 0.153.

The Feature importance acording to the NN is:

    Weight	Feature
    0.5816 ± 0.0218	bsub
    0.3295 ± 0.0091	Lsub
    0.2864 ± 0.0263	asub
    0.2378 ± 0.0107	Thickness
    0.0813 ± 0.0047	acer
    0.0587 ± 0.0036	bcer
    0.0411 ± 0.0015	Lcer
    
The model was deployed using the API Gradio for simple GUI.

### Deep Neural Network (Notebook 4)

The Deep neural network is still under development. In a trial attempt the use of the following parameters 'learning_rate': 0.001614, 'dropout_rate': 0.087819, 'num_hidden_layers': 48, 'neurons_per_layer': 179, 'batch_size': 8, 'activation': 'tanh', 'optimizer': 'adam' found the optimium result. However, only 25 trial were attempt and I am now running 400 trials. Now is 234/400 (Sep 14, 12:28 EDT)

## Conclusion

All models were able to predict the L, a and b of the ceramics according to the different input parameters. The Multivariate Regression using the Decision Tree Regressor obtained the lowest MAE, however, the model seems to be very accurate to predict the shade within the range of the train data. The model is not overfitted but extrapolation of data can lead to wrong predictions

The simple neural network was able to predict the shade values, but since the linear output function can lead to infinity, a function limiting the output was needed since L values can only be from 0 to 100 and a and b values only from -100 to 100. Even with a simple NN, the computational power needed for grid search is massive. It took a few hours to complete. The best architecture has 7 inputs, 2 hidden layers, with 20 and 3 nodes respectevely, using a model fit with batch size of 20 and epochs of 100.

The deep neural network was also able to predict the shade values, and the same limitation on the output funtion was implemented. For the Deep NN, Bayesian Optimization was done instead of GridSearchCV for faster optimization. 400 trials are running and the ideal architeture will be tested later 

#### Outline of project
https://github.com/drmateusrocha/Capstone-Project/tree/main/notebooks

- Notebook 1 - Exploratory Analysis 
- Notebook 2 - Multivariate Regressions (Scikit Learn) 
- Notebook 3 - Simple Neural Network (TensorFlow with GridSearchCV) 
- Notebook 4 - Deep Neural Network (Tensorflow with Bayesian Optimization)


## Citation

If you use this repository, please cite:

> Kose C Jr, Oliveira D, Pereira PNR, Rocha MG. Using artificial intelligence to predict the final color of leucite-reinforced ceramic restorations. *J Esthet Restor Dent.* 2023 Jan;35(1):105-115. doi: [10.1111/jerd.13007](https://doi.org/10.1111/jerd.13007). PMID: 36592128.
