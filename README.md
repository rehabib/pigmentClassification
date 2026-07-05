# pigmentClassification
Automated Finish Classification for Veridian Lacquer Trend Reports
Veridian Lacquer is a boutic nail polish manufacturer seeking to standardize the classification of nail polish 
finishes for their anual state of the shade report. Traditionally, finishes such as Creme, Shimmer, Metallic, and 
Holographic are classified manually, which introduces inconsistency.
The goal of this project is to develop a machine learning model in MATLAB that automatically classifies 
nail polish finishes based on measurable color properties: RGB values (Red, Green, Blue), Opacity (0-100), 
Reflectance Index (0-1). A synthetic dataset is generated to simulate realistic nail polish finish characteristics 
across four categories : Creme, Shimmer, Metallic, and Holographic. Each class was defined using controlled 
ranges of RGB values, opacity levels, and reflectance indices to reflect typical visual properties. To 
ensure consistency and model performance, all numerical features were normalized using standard score 
normalization, which scales the data to have a mean of zero and a standard deviation of one. This step is 
particularly important for distance based algorithm such as k-nearest neighbours (k-NN), ensuring that no 
single feature dispropotionately influence the classification. On Exploratory data analysis, the scatter plots 
reveal distinct clustering patterns among the four finish categories. Metallic and Holographic finishes tend to 
exhibit higher reflective values and on the observation in this feature space, they are clearly separable. Creme 
and Shimmer finishes exhibit some overlap when considering only Red and Reflectance. This indicates that 
additional features such as Green, Blue, Opacity are necessary to fully distinguish between these classes. 
And on the 3D plot since both Metallic and Holographic have high reflectance, overlapping opacity, and RGB 
differences are not strong enough on the given reflectance range. Reflectance ranges were adjusted to 
improve separability between Metallic and Holographic finishes. A slight overlap was intentionally retained to 
simulate realistic conditions where similar finishes may share visual properties, ensuring the classification 
model relies on multiple features rather than a single threshold. 
The dataset is split into training and testing sets to evaluate how well the model generalizes to unseen data. 
An 80/20 split is used for this project as is commonly used to balance training performance and evaluation 
reliability. A k-NN classification model was trained using the normalized feature set. The model was then 
evaluated on unseen test data to assess its generalization performance. The confusion matrix reveals strong 
classification performance, with small number of misclassification. Specifically, a few Shimmer samples were 
incorrectly classified as Creme and Metallic, while some Metallic and Holographic samples were confused with 
each other. Despite these minor overlaps , the overal model accuracy reached 95%, indicating that the selected 
features and classification approach are effective for this task.In addition to the k-NN model, a Decision Tree 
classifier was implemented to compare different approaches to the classification task. While k-NN is a distance 
based algorithm that classifies samples based on similarity in feature space, the Decision Tree model uses a 
series of rule based splits to partition the data. This comparison allows for evaluating how different modelling 
techniques perform on the same dataset and provides insight into the most effective method for distinguishing 
between nail polish finishes.
