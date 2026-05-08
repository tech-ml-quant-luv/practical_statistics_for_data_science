## Lesson 1- Exploratory Data Analysis

- Mean is not always the best measure for central value.
- A metric is essentially a value computed from data (like a mean or median) that data scientists typically call a “metric” and statisticians typically call an "estimate".
- statisticians “use the term estimate for a value calculated from the data at hand” to distinguish it from a theoretical true value, while “data scientists and business analysts are more likely to refer to such a value as a metric.
- N (or n) refers to the total number of records or observations. In statistics it is capitalized if it is referring to a population, and lower‐case if it refers to a sample from a population. In data science, that distinction is not vital, so you may see it both ways.

#### Mean 

- The most basic estimation of the location is the mean or the average value.
- A variation of mean is the trimmed mean, whcih we calcualte by dropping a fixed number of sorted values at each end and then taking an average of the remaining values.
- A trimmed man elimates the influence of extreme values. 
- Another type of mean is a weighted mean, whcih we calculate by multiplying each data value xi by a user-specified weight wi and dividing the sum by the sum of weights. 
    There are two main motivations for using a weighted mean:
• Some values are intrinsically more variable than others, and highly variable
observations are given a lower weight. For example, if we are taking the average
from multiple sensors and one of the sensors is less accurate, then we might
downweight the data from that sensor.
• The data collected does not equally represent the different groups that we are
interested in measuring. For example, because of the way an online experiment
was conducted, we may not have a set of data that accurately reflects all groups in
the user base. To correct that, we can give a higher weight to the values from the
groups that were underrepresented.

#### Median

- The median is the middle number on a sorted list of the data. If there is an even number of data values, the middle value is one that is not actually in the data set, but rather the average of the two values that divide the sorted data into upper and lower halves.
- Compared to the mean, which uses all observations, the median depends only on the values in the center of the sorted data. While this might seem to be a disadvantage, since the mean is much more sensitive to the data, there are many instances in which the median is a better metric for location.
- For the same reasons that one uses a weighted mean, it is also possible to compute a weighted median. As with the median, we first sort the data, although each data value has an associated weight. Instead of the middle number, the weighted median is a value such that the sum of the weights is equal for the lower and upper halves of the sorted list. Like the median, the weighted median is robust to outliers.

#### Outliers

- The media is referred to as a robust estimate of location since it is not influenced by the outliers(extreme cases) that coudl skew the results.
- An outlier is any value that is very distant from the other values in the data set. The exact definition of an outlier is somewhat subjective., althought certain conventions are used in various data summaries and plots.
- Outliers can also be a part fo data errors such as mixing data from different units or bad readings from a sensor. When outliers are results of a bad data, the mean will result in poor estimate of location, while the median will still be valid.
<p style="color: blue">In any case, outliers should be identified and are usually worthy of further investigation.</p>

<i style="color: red">In contrast to typical data analysis, where outliers are sometimes informative and sometimes a nuisance, in anomaly detection the points of interest are the outliers, and the greater mass of data serves primarily to define the “normal” against which anomalies are measured</i>

<i style="color: blue">The median is not the only robust estimate of location. In fact, a trimmed mean is widely used to avoid the influence of outliers. For example, trimming the bottom and top 10% (a common choice) of the data will provide protection against outliers in all but the smallest data sets. The trimmed mean can be thought of as a compromise between the median and the mean: it is robust to extreme values in the data, but uses more data to calculate the estimate for location.</i> 

#### Estimates of Variabilility

- Location is just one dimension in summarizing a feature. A second dimension, variability, also referred to as dispersion, measures whether the data values are tightly clustered or spread out. At the heart of statistics lies variability: measuring it, reducing it, distinguishing random from real variability, identifying the various sources of real variability, and making decisions in the presence of it.