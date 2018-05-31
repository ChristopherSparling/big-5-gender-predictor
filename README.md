# Gender Prediction with Big 5 Personality Traits

<img align="right" width="350" height="250"
     title="big 5 Visualized" src="./images/big-5-personality-traits.png">
     
In the field of clinical psychology there is a generally accepted model known as the "Big 5 Personality Traits" which as the title suggests breaks down human personality along 5 axes: 

- **O**penness to experience : _inventive/curious vs. consistent/cautious_
- **C**oncientiousness : _efficient/organized vs. easy-going/careless_
- **E**xtraversion : _outgoing/energetic vs. solitary/reserved_
- **A**greeableness : _friendly/compassionate vs. challenging/detached_
- **N**euroticism : _sensistve/nervous vs. secure/confident_

Through the use of simple self-reported adjective/charactersitic tests, a percentile score can be determined for each trait. These percentile scores can then be used as feature sets in classification algorithms to predict sex (which is also reported in the test).

The large dataset used for model training and testing is from the [Open Source Psychometrics Project](https://openpsychometrics.org/) \[[raw_data](https://openpsychometrics.org/_rawdata/)\] which:
> _provides a collection of interactive personality tests with detailed results that can be taken for personal entertainment or to learn more about personality assessment_
 
At the time of writing this README there are **19719** responses present in _data.csv_:
````r
data %>% 
    group_by(gender) %>%
    summarise(n_rows = length(gender))

# A tibble: 4 x 2
  gender n_rows
   <int>  <int>
1      0     24 # no response
2      1   7608 # male
3      2  11985 # female
4      3    102 # other
````
The test responses are initially stored in a 57 column dataframe (author's responses shown below in list) with extraneous (though still interesting to explore) data regarding race, age, dominant hand, ISO country code, etc. The various levels and responses of these columns can be investigated furhter in _codebook.txt_.
````r
author <- c(3,21,1,1,1,2,CAN,2,2,4,3,4,2,2,2,4,2,1,4,2,2,1,1,1,2,2,3,2,3,1,2,2,3,2,3,2,3,3,2,4,1,4,1,4,2,4,4,4,1,4,1,3,2,5,4,4,4)
````
