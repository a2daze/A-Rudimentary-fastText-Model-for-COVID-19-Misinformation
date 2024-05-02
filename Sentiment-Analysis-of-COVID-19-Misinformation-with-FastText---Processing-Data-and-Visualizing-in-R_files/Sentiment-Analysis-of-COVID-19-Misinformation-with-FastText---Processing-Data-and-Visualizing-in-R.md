Sentiment Analysis of COVID-19 Misinformation with FastText - Processing
Data and Visualizing in R
================
Alex Zharchuk

``` r
rmarkdown::find_pandoc()
```

    ## $version
    ## [1] '3.1.13'
    ## 
    ## $dir
    ## [1] "/opt/homebrew/bin"

``` r
library(tidyverse)
```

    ## ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ## ✔ dplyr     1.1.4     ✔ readr     2.1.5
    ## ✔ forcats   1.0.0     ✔ stringr   1.5.1
    ## ✔ ggplot2   3.5.0     ✔ tibble    3.2.1
    ## ✔ lubridate 1.9.3     ✔ tidyr     1.3.1
    ## ✔ purrr     1.0.2     
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()
    ## ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

``` r
similarities<-read.csv('/Users/alexz/Sentiment Analysis of COVID-19 Misinformation with FastText/similarity_df.csv')
head(similarities)
```

    ##   X   word1       word2 similarity
    ## 1 0 vaccine         bad  0.2416922
    ## 2 1 vaccine        good  0.2961145
    ## 3 2 vaccine   effective  0.7186649
    ## 4 3 vaccine   dangerous  0.3960435
    ## 5 4 vaccine ineffective  0.7637438
    ## 6 5 vaccine      deadly  0.4159848

``` r
ggplot(data=similarities, aes(word1,word2,fill=similarity))+
  geom_tile()+
  scale_fill_gradient(low='white',high='blue')+
  theme_minimal()+
  theme(axis.text.x=element_text(angle=45,hjust=1))+
  labs(title='Word Similarities')+
  xlab('Word 1')+ylab('Word 2')+ggtitle('Word Similarities') 
```

![](Sentiment-Analysis-of-COVID-19-Misinformation-with-FastText---Processing-Data-and-Visualizing-in-R_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->
