Lenght of Stay
================

### Length of stay for each Physician compared to the Mean of the Team for each month.

The purpose of this quick data exploration is to see if there's a statistically significant difference between the providers when it comes to the length of stay (los) from June 2015 to July 2016.

The 'los' numbers are different, but that begs the question: is that difference between the providers significant or just related to randomness?

For this end, I initially plot the 'los' for each provider side to side with the team's mean 'los' for each month from June 2015 to July 2016. This visualization gives a rough idea about each provider's performance.

Then, I use the ANOVA method to compare the means between the samples. There will be a total of 18 samples each reprensenting one Physician. Each sample has 14 observations corresponding to the mean of the 'los' for each month for each physician from June, 2015 to July, 2016 (14 months total).

The frame below is the source of plotting and analysing the data. I retrieved the data from www.imbills.com and exported it for each month using a csv format.

    ##      AJ   AR   BG   BA   BV   GS   KG   MO   MH   NS   OE   OC   PM   PS
    ## 1  4.21 3.80   NA 4.88 3.46 5.18 5.80 4.17 6.57   NA 4.36   NA 4.54   NA
    ## 2  4.00 4.02 5.54 6.69 4.75 6.15 4.00 4.74 6.14   NA 5.80   NA 4.38 6.47
    ## 3  5.16 4.45 5.07 6.14 5.20 4.74 5.33 9.67 7.18   NA 4.97   NA 5.07 7.90
    ## 4  3.48 4.00 4.95 7.78 6.28 4.76 3.78 4.98 7.00 4.31 6.02   NA 4.20 4.91
    ## 5  3.95 3.77 5.86 6.61 5.58 4.65 3.87 7.44 6.76 4.24 4.53   NA 4.36 5.85
    ## 6  5.08 5.02 3.46 5.51 6.61 5.33 4.42 4.30 6.10 5.13 4.84   NA 5.11 5.96
    ## 7  6.40 5.36 4.98 7.65 5.70 5.80 4.42 4.49 5.54 5.05 3.47 5.49 5.19 6.78
    ## 8  4.56 6.08 4.85 6.57 4.56 5.25 4.42 4.22 7.07 4.38 6.81 8.13 4.65 6.00
    ## 9  5.11 4.02 4.13 4.83 7.83 5.27 5.83 4.50 5.67 4.33 5.52 6.27 4.24 8.00
    ## 10 5.94 3.96 3.74 4.38 4.63 5.87 3.87 5.42 5.95 4.22 4.81 5.23 3.67 7.61
    ## 11 4.71 4.40 3.75 4.76 8.41 4.93 3.89 4.35 5.40 5.93 4.38 6.24 4.58 5.51
    ## 12 4.56 5.40 5.05 6.02 4.89 4.18 5.27 3.54 5.39 5.04 4.48 7.07 5.67 4.50
    ## 13 5.26 3.09 3.00 5.52 6.19 5.38 4.89   NA 6.23 4.84 6.41 6.88 4.25 5.07
    ## 14 4.47 3.92 3.73 5.59 5.10 6.28 7.83   NA 5.94 5.26   NA 4.69 4.78 7.79
    ##      RR   SR   TS   ZM
    ## 1  4.32 4.53   NA 4.47
    ## 2  4.53 4.28 4.75 4.82
    ## 3  3.88 4.53 5.65 5.33
    ## 4  4.07 5.72 5.68 4.87
    ## 5  3.68 6.25 4.32 4.96
    ## 6  3.31 6.75 6.68 6.35
    ## 7  3.97 5.40 4.93 6.15
    ## 8  4.21 5.75 6.19 7.74
    ## 9  4.93 4.86 4.23 6.55
    ## 10 4.05 4.00 5.30 6.38
    ## 11 3.74 4.35 4.18 3.66
    ## 12 5.24 4.56 4.94 5.76
    ## 13 3.45 4.16 6.93 8.45
    ## 14 6.88 6.57 4.97 8.00

    ## Source: local data frame [14 x 4]
    ## 
    ##    values.1 mean_per_month median_per_month     n
    ##       (dbl)          (dbl)            (dbl) (int)
    ## 1         1       4.637692            4.470    18
    ## 2         2       5.066250            4.750    18
    ## 3         3       5.641875            5.180    18
    ## 4         4       5.105294            4.910    18
    ## 5         5       5.098824            4.650    18
    ## 6         6       5.291765            5.130    18
    ## 7         7       5.376111            5.380    18
    ## 8         8       5.635556            5.500    18
    ## 9         9       5.340000            5.020    18
    ## 10       10       4.946111            4.720    18
    ## 11       11       4.842778            4.490    18
    ## 12       12       5.086667            5.045    18
    ## 13       13       5.294118            5.260    18
    ## 14       14       5.737500            5.425    18

![](Figs/unnamed-chunk-5-1.png)

### Barplots for each physician compared to the team's mean 'los'.

AJ bar chart
------------

![](Figs/unnamed-chunk-6-1.png)

    ##      values  ind  m
    ## 1  4.210000   AJ  1
    ## 2  4.000000   AJ  2
    ## 3  5.160000   AJ  3
    ## 4  3.480000   AJ  4
    ## 5  3.950000   AJ  5
    ## 6  5.080000   AJ  6
    ## 7  6.400000   AJ  7
    ## 8  4.560000   AJ  8
    ## 9  5.110000   AJ  9
    ## 10 5.940000   AJ 10
    ## 11 4.710000   AJ 11
    ## 12 4.560000   AJ 12
    ## 13 5.260000   AJ 13
    ## 14 4.470000   AJ 14
    ## 15 4.637692 Team  1
    ## 16 5.066250 Team  2
    ## 17 5.641875 Team  3
    ## 18 5.105294 Team  4
    ## 19 5.098824 Team  5
    ## 20 5.291765 Team  6
    ## 21 5.376111 Team  7
    ## 22 5.635556 Team  8
    ## 23 5.340000 Team  9
    ## 24 4.946111 Team 10
    ## 25 4.842778 Team 11
    ## 26 5.086667 Team 12
    ## 27 5.294118 Team 13
    ## 28 5.737500 Team 14

AR bar chart
------------

![](Figs/unnamed-chunk-7-1.png)

BG bar chart
------------

![](Figs/unnamed-chunk-8-1.png)

BA bar chart
------------

![](Figs/unnamed-chunk-9-1.png)

BV bar chart
------------

![](Figs/unnamed-chunk-10-1.png)

GS bar chart
------------

![](Figs/unnamed-chunk-11-1.png)

KG bar chart
------------

![](Figs/unnamed-chunk-12-1.png)

    ## <ScaleContinuousPosition>
    ##  Range:  
    ##  Limits:    0 --    1

MO bar chart
------------

![](Figs/unnamed-chunk-13-1.png)

MH bar chart
------------

![](Figs/unnamed-chunk-14-1.png)

NS bar chart
------------

![](Figs/unnamed-chunk-15-1.png)

OE bar chart
------------

![](Figs/unnamed-chunk-16-1.png)

OC bar chart
------------

![](Figs/unnamed-chunk-17-1.png)

PM bar chart
------------

![](Figs/unnamed-chunk-18-1.png)

PS bar chart
------------

![](Figs/unnamed-chunk-19-1.png)

RR bar chart
------------

![](Figs/unnamed-chunk-20-1.png)

SO bar chart
------------

![](Figs/unnamed-chunk-21-1.png)

TS bar chart
------------

![](Figs/unnamed-chunk-22-1.png)

ZM bar chart
------------

![](Figs/unnamed-chunk-23-1.png)

Mean of Length of Stay by ascending order
-----------------------------------------

    | RR    4.304286
    | AR    4.377857
    | BG    4.470000
    | PM    4.620714
    | AJ    4.777857
    | NS    4.793636
    | KG    4.830000
    | OE    5.107692
    | SR    5.122143
    | MO    5.151667
    | GS    5.269286
    | TS    5.288462
    | BV    5.656429
    | BA    5.923571
    | ZM    5.963571
    | MH    6.210000
    | OC    6.250000
    | PS    6.334615

### Using ANOVA and Tukey HSD

In order find out if there's a significant difference between the above 18 physicians, I used the ANOVA method to compare the means of the different 18 samples. As mentioned above each sample represents one physician with 14 values each corresponding to the 'los' for one month (total of 14 months). The P value (depicted below as Pr(&gt;F)) returned was 1.31 \* 10 to the power -12, which was way smaller than the treshold of 0.05. This indicates that there's a significant difference between At Least TWO means of the 18 samples.

Now a post hoc test called Tukey's HSD was conducted in order identify which samples differ significantly (by comparing all possible combinations of sample pairs-meaning comparing each provider with the other). It amounts to a total of 153 combinations or commparisons.

For instance if we have 3 samples (P1,P2,P3), there will be 3 total combinations: P1 compared with P2, P1 compared with P3 and P2 compared with P3.

In our case of 18 samples, we have 153 combinations to compare. TukeyHSD identified an overall significant difference between the bottom 8 providers compared with the first 10.

    ##              Df Sum Sq Mean Sq F value   Pr(>F)    
    ## ind          17  105.6   6.210   6.531 1.31e-12 ***
    ## Residuals   234  222.5   0.951                     
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

After I eliminated providers with length of stay exceeding 5.2, I ran ANOVA again on the remaining dataset of 10 physicians. This time the P value defined below as *Pr(&gt;F)* was 0.141 indicating that the 'los' difference between the remaining physician is NOT significant (P less than 0.05 is usually the treshold for significance) and is likely due to randomness.

    ##              Df Sum Sq Mean Sq F value Pr(>F)
    ## ind           9  12.16  1.3515   1.539  0.141
    ## Residuals   130 114.19  0.8784

### Conclusion

Shortfalls of this data analysis:

This data exploration is in no way comprehensive or conclusive. In order to run ANOVA, the 'los' variable for each sample should have a normal distribution. I assumed 'los' follows a normal distribution since it's related to human behavior. In order to run ANOVA, the missing values for providers who were not working on certain months, were replaced by the mean of their 'los' computed from the months when they were working. The data might be unfair for some providers like Dr. BA and OC whose 'los' has been improving over the last few months (it is not unusual for someone who newly joined the team to have high 'los' in the first few months). The data might be unfair to people who had more float rotations and therefore carried more ICU patients compared to people who had more geographical rotations especially if they had more rotations on the Neurology unit.

I was always suspicious that there's an inter-physician difference in performance and if there is, it could merely be a random observation. This data doesn't prove or disprove that, however it shows that there's a significant difference between a physician with an 'los' of 4.5 and one with an 'los' higher than 6.2; and this particular finding may not be related solely to randomness.
