# Topic modeling the 10,000 top-performing news articles on social media published between Nov. 2016 and May 2017

Using the **topicmodels** and **quanteda** packages, I attempted to predict news topics from the headlines of 10,000 top-performing news articles written between Nov. 2016 and May 2017 and downloaded from NewsWhip. 

Here, a selection of top terms from three of the predicted topics.

```
> terms[,19]
 [1] "clinton"         "an"              "george"          "family"         
 [5] "michael"         "hillary"         "snl"             "trump"          
 [9] "hillary_clinton" "george_michael"  "'_snl"           "snl_'"          
[13] "baldwin"    

> terms[,34]
 [1] "national"             "media"                "climate"             
 [4] "change"               "pipeline"             "security"            
 [7] "dakota"               "access"               "climate_change"      
[10] "protest"              "protesters"           "administration"      
[13] "dakota_access"        "social"               "trump_administration"

> terms[,28]
 [1] "bill"        "health"      "care"        "gop"         "would"      
 [6] "plan"        "vote"        "obamacare"   "to"          "republicans"
[11] "tax"         "health_care" "republican"  "from"        "for" 
```

These three topics would seem to scoop up stories on **Hillary Clinton**, the **Dakota Access Pipeline**, and **health care**. (Of course, confounding terms end up in these topics, too. Stories on George Michael's December 25, 2016 death, for example, get dumped into stories about Clinton, who saw a surge of coverage following her loss in the 2016 Presidential election.)

## Plotting article topics across time

Of 50 topics predicted, most were junk. I chose to plot eight that saw peaks of coverage with more than 10 articles on a single day. Those are **Clinton, Dakota Access, Health Care, Immigration, Meryl Streep, the Women's March, White House** and **Donald Trump**.

![img](http://aleszu.com/textualanalysis/top500-plots/clinton.png)
![img](http://aleszu.com/textualanalysis/top500-plots/dakotaaccess.png)
![img](http://aleszu.com/textualanalysis/top500-plots/healthcare.png)
![img](http://aleszu.com/textualanalysis/top500-plots/immigration.png)
![img](http://aleszu.com/textualanalysis/top500-plots/merylstreep.png)
![img](http://aleszu.com/textualanalysis/top500-plots/womensmarch.png)
![img](http://aleszu.com/textualanalysis/top500-plots/whitehouse.png)
![img](http://aleszu.com/textualanalysis/top500-plots/trump.png)

## Trump appears in several topics 

Unsurprisingly, stories about **Donald Trump** dominate news coverage between Nov. 2016 and May 2017. They also appear in multiple topics.

```
> terms[,13]
 [1] "trump"       "house"       "white"       "white_house" ":"          
 [6] "russia"      "to"          "report"      "election"    "russian"    
[11] "trumps"      "help"        "press"       "team"        "conway"  

> terms[,48]
 [1] "trump"           "donald"          "president"       ":"              
 [5] "donald_trump"    "inauguration"    "trump's"         "trump_:"        
 [9] ":_trump"         "president_trump" "trump_,"         "trump_is"       
[13] "to_trump"        "claims"          "trump_to" 
```

## Topic modeling pick up mostly "hard" news

This topic modeling shows that of the most popular topics across time, most can be categorized as "hard" news. Of these eight topics, only "Meryl Streep" might be considered "soft," although the peak in news coverage mentioning Streep came in the wake of her [comments](http://www.cnn.com/2017/01/08/entertainment/meryl-streep-golden-globes-speech/index.html) at the Golden Globes about Donald Trump, arguably "hard" news.

## Looking at social shares by topic

I ran a Excel pivot table of predicted topics by total social shares. Trump, health care and Dakota Access were most popular in this dataset.  

![img](http://aleszu.com/textualanalysis/top500-plots/socialshares.png)

## Looking at topics by publisher

Using an Excel pivot table, I created this heatmap of coverage by topic. Some findings: The Huffington Post disproportionately covered Meryl Streep and Clinton while BuzzFeed disproportionately covered the Women's March. The New York Times and The Hill covered health care almost equally while CNN covered immigration more than any other topic. 

![img](http://aleszu.com/textualanalysis/top500-plots/topics-plotted.png)

## How we decided on 50 topics 

Using the methods described by [Pablo Barberá](https://github.com/pablobarbera/eui-text-workshop/blob/master/03-unsupervised/01-topic-models.Rmd), we plotted the numbers of topics against perplexity. This plot serves as a justification for sampling just above or below 30 topics. 50 is more or less within that range.

![img](http://aleszu.com/textualanalysis/top500-plots/topicsperplexity.png)

# Output of the top terms from 50 topics 

```
>
> terms[,1]
 [1] "state"              "planned"            "planned_parenthood"
 [4] "parenthood"         "over"               "case"              
 [7] "london"             "days"               "protest"           
[10] "cant"               "marriage"           "not"               
[13] "california"         "they_are"           "cat"               
>
> terms[,2]
 [1] "as"         "mike"       "pence"      "against"    "mike_pence" "that"      
 [7] "live"       "during"     "for"        "putin"      "leader"     "donates"   
[13] "benefit"    "toddler"    "j"         
>
> terms[,3]
 [1] "of"       ","        "-"        "india"    "times"    ":"        "of_india"
 [8] "times_of" "-_times"  "see"      "khan"     "as"       "rs"       "indian"  
[15] "pics"    
>
> terms[,4]
 [1] "all"     "to"      "goes"    "in"      "twitter" "viral"   ":"      
 [8] "on"      "plans"   "class"   "poor"    "to_take" "again"   "student"
[15] "take"   
>
> terms[,5]
 [1] "in"       "and"      "2017"     "live"     "ipl"      "china"    "facebook"
 [8] "2017_:"   "12"       "birth"    "ipl_2017" "to"       "final"    "in_2017" 
[15] "lose"    
>
> terms[,6]
 [1] "'"     ":"     ":_'"   ",_'"   "us"    "'_:"   "a_'"   "to_'"  "'_the"
[10] "'_to"  "'_in"  "on_'"  "of_'"  "'_and" "'_is" 
>
> terms[,7]
 [1] "from"      "big"       "get"       "fans"      "class"     "woman"    
 [7] "attacks"   "mom"       "there"     "tells"     "message"   "sanctuary"
[13] "tree"      "letter"    "hollywood"
>
> terms[,8]
 [1] "new"      "about"    "we"       "all"      "to"       "need"     "college" 
 [8] "what"     "know"     "york"     "need_to"  "the_new"  "new_york" "now"     
[15] "talk"    
>
> terms[,9]
 [1] "you"    "that"   "?"      "will"   "your"   "if"     "and"    "make"  
 [9] "can"    "get"    "are"    "this"   "things" "only"   "why"   
>
> terms[,10]
 [1] "to"      "$"       "in"      "million" "1"       "billion" "for"    
 [8] "100"     "deal"    "under"   "cut"     "great"   "for_$"   "a"      
[15] "say"    
>
> terms[,11]
 [1] "a"     "is"    "|"     "this"  "it"    "and"   "was"   "her"   "has"  
[10] "not"   "woman" "what"  "but"   "an"    "she"  
>
> terms[,12]
 [1] "us"         "into"       "attack"     "%"          "over"       "already"   
 [7] "female"     "give"       "navy"       "them"       "police"     "car"       
[13] "republican" "happy"      "tears"     
>
> terms[,13]
 [1] "trump"       "house"       "white"       "white_house" ":"          
 [6] "russia"      "to"          "report"      "election"    "russian"    
[11] "trumps"      "help"        "press"       "team"        "conway"     
>
> terms[,14]
 [1] "."       "to"      "u.s"     "u.s_."   "in"      "for"     "trump"  
 [8] "._."     "now"     "wall"    "pay"     "they"    "mexico"  "wants"  
[15] "the_u.s"
>
> terms[,15]
 [1] "his"          "with"         "show"         "dog"          "man"         
 [6] "of_his"       "sharma"       "for"          "own"          "kapil"       
[11] "him"          "kapil_sharma" "his_own"      "sunil"        "ohio"        
>
> terms[,16]
 [1] "sanders"        "bernie"         "bernie_sanders" "big"           
 [5] "town"           "voter"          "democratic"     "because"       
 [9] "fraud"          "voter_fraud"    "down"           "with"          
[13] ":"              "into"           "him"           
>
> terms[,17]
 [1] "to"             "court"          "north"          "supreme"       
 [5] "supreme_court"  "back"           "on"             "of"            
 [9] "muslim"         "into"           "carolina"       "korea"         
[13] "rules"          "north_carolina" "war"           
>
> terms[,18]
 [1] "in"        "from"      "americans" "trump"     "its"       "why"      
 [7] "5"         "obamas"    "illegal"   "like"      "being"     "lost"     
[13] "victims"   "50"        "british"  
>
> terms[,19]
 [1] "clinton"         "an"              "george"          "family"         
 [5] "michael"         "hillary"         "snl"             "trump"          
 [9] "hillary_clinton" "george_michael"  "'_snl"           "snl_'"          
[13] "baldwin"         "win"             "day"            
>
> terms[,20]
 [1] "after"           "star"            "attack"          "carrie"         
 [5] "fisher"          "in"              "carrie_fisher"   "mother"         
 [9] "daughter"        "60"              "reynolds"        "wars"           
[13] "actress"         "debbie_reynolds" "a_-"            
>
> terms[,21]
 [1] "-"        "news"     "bbc"      "-_bbc"    "bbc_news" "year"     "old"     
 [8] "-_year"   "-_old"    "year_-"   "girl"     "fake"     "us"       "boy"     
[15] "'_-"     
>
> terms[,22]
 [1] "to"      "up"      "from"    ","       "for"     "up_to"   "it"     
 [8] "law"     ":"       "party"   "were"    "give"    "with"    "america"
[15] "top"    
>
> terms[,23]
 [1] "first"     "for"       ","         "day"       "time"      "2"        
 [7] "its"       "office"    "black"     ":"         "on"        "the_first"
[13] "baahubali" "free"      "set"      
>
> terms[,24]
 [1] "after"     "years"     "still"     "states"    "united"    "on"       
 [7] "50"        "off"       "kids"      "flight"    "airlines"  "years_of" 
[13] "gets"      "passenger" "wins"     
>
> terms[,25]
 [1] "to"       "how"      "back"     "go"       "how_to"   "being"    "fight"   
 [8] "ready"    "ready_to" "to_go"    "who"      "to_fight" "them"     "stand"   
[15] "back_to" 
>
> terms[,26]
 [1] "are"           "on"            "people"        "march"        
 [5] "their"         "who"           "women's"       "women"        
 [9] "women's_march" "washington"    "people_are"    "and"          
[13] "womens"        "scientists"    "say"          
>
> terms[,27]
 [1] "more"      "than"      "over"      "more_than" "shows"     "on"       
 [7] "and"       "wwe"       "votes"     "couple"    "americans" "money"    
[13] "a"         "him"       "percent"  
>
> terms[,28]
 [1] "bill"        "health"      "care"        "gop"         "would"      
 [6] "plan"        "vote"        "obamacare"   "to"          "republicans"
[11] "tax"         "health_care" "republican"  "from"        "for"        
>
> terms[,29]
 [1] "!"               "just"            "trump"           "news"           
 [5] "*"               "liberty"         "writers"         "what"           
 [9] "*_liberty"       "liberty_writers" "writers_news"    "&"              
[13] "has"             "sessions"        "breaking"       
>
> terms[,30]
 [1] "by"        "with"      "trump's"   "end"       "senate"    "24"       
 [7] "isis"      "some"      "an"        "parents"   "meeting"   "stunning" 
[13] "different" "turns"     "christmas"
>
> terms[,31]
 [1] "with"        "for"         "school"      "of"          "trumps"     
 [6] "secretary"   "devos"       "betsy"       "education"   "high"       
[11] "students"    "public"      "betsy_devos" "over"        "off"        
>
> terms[,32]
 [1] "to"        "on"        "against"   "coming"    "free"      "where"    
 [7] "coming_to" "chicago"   "takes"     "all"       "top"       "sex"      
[13] "must"      "farewell"  "is_coming"
>
> terms[,33]
 [1] ":"              "watch"          "video"          "and"           
 [5] "from"           "]"              "["              "video_]"       
 [9] "[_video"        "him"            "judicial"       "judicial_watch"
[13] "out"            "watch_:"        "-_judicial"    
>
> terms[,34]
 [1] "national"             "media"                "climate"             
 [4] "change"               "pipeline"             "security"            
 [7] "dakota"               "access"               "climate_change"      
[10] "protest"              "protesters"           "administration"      
[13] "dakota_access"        "social"               "trump_administration"
>
> terms[,35]
 [1] "the"       "of"        "is"        "of_the"    "in_the"    "world"    
 [7] "in"        "most"      "best"      "on_the"    "2016"      "for_the"  
[13] "to_the"    ":_the"     "the_world"
>
> terms[,36]
 [1] "obama"          "of"             "in"             "from"          
 [5] "women"          "michelle"       "barack"         "michelle_obama"
 [9] "official"       "girls"          "two"            "barack_obama"  
[13] "5"              "obama's"        "oil"           
>
> terms[,37]
 [1] "with"         "-_the"        "baby"         "boston"       "globe"       
 [6] "the_boston"   "boston_globe" "its"          "kapoor"       "off"         
[11] "drug"         "ali"          ","            "gets"         "kareena"     
>
> terms[,38]
 [1] "to"            "speech"        "golden"        "for"          
 [5] "and"           "meryl"         "meryl_streep"  "streep"       
 [9] "7"             "globes"        "golden_globes" "fire"         
[13] "in"            "america"       "together"     
>
> terms[,39]
 [1] "in"        "man"       "of"        "police"    "death"     "found"    
 [7] "life"      "killed"    "who"       "by"        "black"     "officer"  
[13] "shooting"  "killed_in" "to_death" 
>
> terms[,40]
 [1] "from"     "trumps"   "at"       "on"       "west"     "civil"    "man_who" 
 [8] "michigan" "kind"     "storm"    "rights"   "calls"    "final"    "city"    
[15] "shocked" 
>
> terms[,41]
 [1] "no"        ","         "one"       "("         ")"         "over"     
 [7] "no_longer" "longer"    "exclusive" "face"      "female"    "wedding"  
[13] "no_one"    "is_no"     "refugee"  
>
> terms[,42]
 [1] ":"        "i"        "out"      "my"       "on"       "at"       "out_of"  
 [8] ":_i"      "fox"      "fox_news" "love"     "dont"     "home"     "am"      
[15] "i_am"    
>
> terms[,43]
 [1] ","         "at"        "and"       "dies"      "dies_at"   "dead"     
 [7] ",_dies"    ",_and"     "john"      "actor"     "aged"      "dead_at"  
[13] "age"       "dies_aged" "singer"   
>
> terms[,44]
 [1] "on"              "trump's"         "ban"             "of"             
 [5] "order"           "immigration"     "signs"           "executive"      
 [9] "travel"          "judge"           "refugees"        "federal"        
[13] "abortion"        "executive_order" "trudeau"        
>
> terms[,45]
 [1] "be"      "says"    ","       "will"    "have"    "he"      "not"    
 [8] "to_be"   "should"  "may"     "could"   "why"     ",_says"  "been"   
[15] "will_be"
>
> terms[,46]
 [1] "for"       "who"       "calls"     "for_trump" "budget"    "calls_for"
 [7] "secret"    "voted"     "service"   ":"         "take"      "air"      
[13] "every"     "|"         "science"  
>
> terms[,47]
 [1] "anti_-"     "anti"       "on"         "-_trump"    "california" "an"        
 [7] "tv"         "online"     "rally"      "dad"        "after"      "had"       
[13] "protests"   "trumps"     "all"       
>
> terms[,48]
 [1] "trump"           "donald"          "president"       ":"              
 [5] "donald_trump"    "inauguration"    "trump's"         "trump_:"        
 [9] ":_trump"         "president_trump" "trump_,"         "trump_is"       
[13] "to_trump"        "claims"          "trump_to"       
>
> terms[,49]
 [1] "on"        "after"     ":"         "meals"     "has"       "wheels"   
 [7] "on_wheels" "american"  "our"       "food"      "meals_on"  "put"      
[13] "over"      "her"       "own"      
>
> terms[,50]
 [1] "to"        "right"     "stop"      "christmas" ":"         "john"     
 [7] "photo"     "wing"      "wanted"    "saying"    "far"       "other"    
[13] "french"    "to_stop"   "'_right" 
```

# All the code

```
library(tidytext)
library(dplyr)
library(stringr)

# Topic models with CSV on "headlines"
# Based on https://github.com/pablobarbera/eui-text-workshop/blob/master/03-unsupervised/01-topic-models.Rmd

library(topicmodels)
top500topics <- read.csv("top500_datetime.csv", stringsAsFactors = FALSE)
library(quanteda)
top500corpus <- corpus(top500topics$Headline)
top500dfm <- dfm(top500corpus, ngrams=c(1,2), ignoredFeatures=stopwords("english"))
top500dfm <- trim(top500dfm, minDoc = 2)

# we now export to a format that we can run the topic model with
dtm <- convert(top500dfm, to="topicmodels")

# estimate LDA with 50 topics
K <- 50
lda <- LDA(dtm, k = K, method = "Gibbs", 
           control = list(verbose=25L, seed = 123, burnin = 100, iter = 500))

topics <- get_topics(lda, 1)
head(topics)

# Add predicted topic column to dataset

top500topics$pred_topic <- topics

# Topics generated (these are manually organized by looking at top terms for each topic)

# Planned Parenthood, 1
# Mike Pence, 2
# White House, 13
# Supreme Court, 17
# Clinton, 19
# Women's March, 26
# Health Care, 28
# Betsy DeVos, 31
# Dakota Access, 34
# Obama, 36
# Meryl Streep, 38
# Police, 39
# Immigration, 44
# Trump, 48

# Inspect terms within topics
terms <- get_terms(lda, 15)
terms[,1]
terms <- get_terms(lda, 15)
terms[,2]
terms <- get_terms(lda, 15)
terms[,3]
terms <- get_terms(lda, 15)
terms[,4]
terms <- get_terms(lda, 15)
terms[,5]
terms <- get_terms(lda, 15)
terms[,6]
terms <- get_terms(lda, 15)
terms[,7]
terms <- get_terms(lda, 15)
terms[,8]
terms <- get_terms(lda, 15)
terms[,9]
terms <- get_terms(lda, 15)
terms[,10]
terms <- get_terms(lda, 15)
terms[,11]
terms <- get_terms(lda, 15)
terms[,12]
terms <- get_terms(lda, 15)
terms[,13]
terms <- get_terms(lda, 15)
terms[,14]
terms <- get_terms(lda, 15)
terms[,15]
terms <- get_terms(lda, 15)
terms[,16]
terms <- get_terms(lda, 15)
terms[,17]
terms <- get_terms(lda, 15)
terms[,18]
terms <- get_terms(lda, 15)
terms[,19]
terms <- get_terms(lda, 15)
terms[,20]
terms <- get_terms(lda, 15)
terms[,21]
terms <- get_terms(lda, 15)
terms[,22]
terms <- get_terms(lda, 15)
terms[,23]
terms <- get_terms(lda, 15)
terms[,24]
terms <- get_terms(lda, 15)
terms[,25]
terms <- get_terms(lda, 15)
terms[,26]
terms <- get_terms(lda, 15)
terms[,27]
terms <- get_terms(lda, 15)
terms[,28]
terms <- get_terms(lda, 15)
terms[,29]
terms <- get_terms(lda, 15)
terms[,30]
terms <- get_terms(lda, 15)
terms[,31]
terms <- get_terms(lda, 15)
terms[,32]
terms <- get_terms(lda, 15)
terms[,33]
terms <- get_terms(lda, 15)
terms[,34]
terms <- get_terms(lda, 15)
terms[,35]
terms <- get_terms(lda, 15)
terms[,36]
terms <- get_terms(lda, 15)
terms[,37]
terms <- get_terms(lda, 15)
terms[,38]
terms <- get_terms(lda, 15)
terms[,39]
terms <- get_terms(lda, 15)
terms[,40]
terms <- get_terms(lda, 15)
terms[,41]
terms <- get_terms(lda, 15)
terms[,42]
terms <- get_terms(lda, 15)
terms[,43]
terms <- get_terms(lda, 15)
terms[,44]
terms <- get_terms(lda, 15)
terms[,45]
terms <- get_terms(lda, 15)
terms[,46]
terms <- get_terms(lda, 15)
terms[,47]
terms <- get_terms(lda, 15)
terms[,48]
terms <- get_terms(lda, 15)
terms[,49]
terms <- get_terms(lda, 15)
terms[,50]

# Inspect topic terms and random article

paste(terms[,1], collapse=", ")
sample(top500topics$Headline[topics==1], 1)
paste(terms[,2], collapse=", ")
sample(top500topics$Headline[topics==2], 1)
paste(terms[,3], collapse=", ")
sample(top500topics$Headline[topics==3], 1)
paste(terms[,4], collapse=", ")
sample(top500topics$Headline[topics==4], 1)
paste(terms[,5], collapse=", ")
sample(top500topics$Headline[topics==5], 1)
paste(terms[,6], collapse=", ")
sample(top500topics$Headline[topics==6], 1)
paste(terms[,7], collapse=", ")
sample(top500topics$Headline[topics==7], 1)
paste(terms[,8], collapse=", ")
sample(top500topics$Headline[topics==8], 1)
paste(terms[,9], collapse=", ")
sample(top500topics$Headline[topics==9], 1)
paste(terms[,10], collapse=", ")
sample(top500topics$Headline[topics==10], 1)
paste(terms[,11], collapse=", ")
sample(top500topics$Headline[topics==11], 1)
paste(terms[,12], collapse=", ")
sample(top500topics$Headline[topics==12], 1)
paste(terms[,13], collapse=", ")
sample(top500topics$Headline[topics==13], 1)
paste(terms[,14], collapse=", ")
sample(top500topics$Headline[topics==14], 1)
paste(terms[,15], collapse=", ")
sample(top500topics$Headline[topics==15], 1)
paste(terms[,16], collapse=", ")
sample(top500topics$Headline[topics==16], 1)
paste(terms[,14], collapse=", ")
sample(top500topics$Headline[topics==14], 1)
paste(terms[,15], collapse=", ")
sample(top500topics$Headline[topics==15], 1)
paste(terms[,16], collapse=", ")
sample(top500topics$Headline[topics==16], 1)
paste(terms[,17], collapse=", ")
sample(top500topics$Headline[topics==17], 1)
paste(terms[,18], collapse=", ")
sample(top500topics$Headline[topics==18], 1)
paste(terms[,19], collapse=", ")
sample(top500topics$Headline[topics==19], 1)
paste(terms[,20], collapse=", ")
sample(top500topics$Headline[topics==20], 1)
paste(terms[,21], collapse=", ")
sample(top500topics$Headline[topics==21], 1)
paste(terms[,22], collapse=", ")
sample(top500topics$Headline[topics==22], 1)
paste(terms[,23], collapse=", ")
sample(top500topics$Headline[topics==23], 1)
paste(terms[,24], collapse=", ")
sample(top500topics$Headline[topics==24], 1)
paste(terms[,25], collapse=", ")
sample(top500topics$Headline[topics==25], 1)
paste(terms[,26], collapse=", ")
sample(top500topics$Headline[topics==26], 1)
paste(terms[,27], collapse=", ")
sample(top500topics$Headline[topics==27], 1)
paste(terms[,28], collapse=", ")
sample(top500topics$Headline[topics==28], 1)
paste(terms[,29], collapse=", ")
sample(top500topics$Headline[topics==29], 1)
paste(terms[,30], collapse=", ")
sample(top500topics$Headline[topics==30], 1)
paste(terms[,31], collapse=", ")
sample(top500topics$Headline[topics==31], 1)
paste(terms[,32], collapse=", ")
sample(top500topics$Headline[topics==32], 1)
paste(terms[,33], collapse=", ")
sample(top500topics$Headline[topics==33], 1)
paste(terms[,34], collapse=", ")
sample(top500topics$Headline[topics==34], 1)
paste(terms[,35], collapse=", ")
sample(top500topics$Headline[topics==35], 1)
paste(terms[,36], collapse=", ")
sample(top500topics$Headline[topics==36], 1)
paste(terms[,37], collapse=", ")
sample(top500topics$Headline[topics==37], 1)
paste(terms[,38], collapse=", ")
sample(top500topics$Headline[topics==38], 1)
paste(terms[,39], collapse=", ")
sample(top500topics$Headline[topics==39], 1)
paste(terms[,40], collapse=", ")
sample(top500topics$Headline[topics==40], 1)
paste(terms[,41], collapse=", ")
sample(top500topics$Headline[topics==41], 1)
paste(terms[,42], collapse=", ")
sample(top500topics$Headline[topics==42], 1)
paste(terms[,43], collapse=", ")
sample(top500topics$Headline[topics==43], 1)
paste(terms[,44], collapse=", ")
sample(top500topics$Headline[topics==44], 1)
paste(terms[,45], collapse=", ")
sample(top500topics$Headline[topics==45], 1)
paste(terms[,46], collapse=", ")
sample(top500topics$Headline[topics==46], 1)
paste(terms[,47], collapse=", ")
sample(top500topics$Headline[topics==47], 1)
paste(terms[,48], collapse=", ")
sample(top500topics$Headline[topics==48], 1)
paste(terms[,49], collapse=", ")
sample(top500topics$Headline[topics==49], 1)
paste(terms[,50], collapse=", ")
sample(top500topics$Headline[topics==50], 1)

# Write CSV with new column of predicted topics 

write.csv(top500topics, file = "top500with50predictedtopicsnew.csv")




# ****** Understanding how many topics we should use by looking at perplexity *******

require(cvTools)
cvLDA <- function(Ntopics,dtm,K=10) {
  folds<-cvFolds(nrow(dtm),K,1)
  perplex <- rep(NA,K)
  llk <- rep(NA,K)
  for(i in unique(folds$which)){
    cat(i, " ")
    which.test <- folds$subsets[folds$which==i]
    which.train <- {1:nrow(dtm)}[-which.test]
    dtm.train <- dtm[which.train,]
    dtm.test <- dtm[which.test,]
    lda.fit <- LDA(dtm.train, k=Ntopics, method="Gibbs",
                   control=list(verbose=50L, iter=100))
    perplex[i] <- perplexity(lda.fit,dtm.test)
    llk[i] <- logLik(lda.fit)
  }
  return(list(K=Ntopics,perplexity=perplex,logLik=llk))
}

# ****** Note: this takes 15 minutes *****

K <- c(20, 30, 40, 50, 60, 70, 80)

results <- list()

i = 1
for (k in K){
  cat("\n\n\n##########\n ", k, "topics", "\n")
  res <- cvLDA(k, dtm)
  results[[i]] <- res
  i = i + 1
}

df <- data.frame(
  k = rep(K, each=10),
  perp =  unlist(lapply(results, '[[', 'perplexity')),
  loglk = unlist(lapply(results, '[[', 'logLik')),
  stringsAsFactors=F)

min(df$perp)
df$ratio_perp <- df$perp / max(df$perp)
df$ratio_lk <- df$loglk / min(df$loglk)

df <- data.frame(cbind(
  aggregate(df$ratio_perp, by=list(df$k), FUN=mean),
  aggregate(df$ratio_perp, by=list(df$k), FUN=sd)$x,
  aggregate(df$ratio_lk, by=list(df$k), FUN=mean)$x,
  aggregate(df$ratio_lk, by=list(df$k), FUN=sd)$x),
  stringsAsFactors=F)
names(df) <- c("k", "ratio_perp", "sd_perp", "ratio_lk", "sd_lk")

library(reshape)
pd <- melt(df[,c("k","ratio_perp", "ratio_lk")], id.vars="k")
pd2 <- melt(df[,c("k","sd_perp", "sd_lk")], id.vars="k")
pd$sd <- pd2$value
levels(pd$variable) <- c("Perplexity", "LogLikelihood")

library(ggplot2)
library(grid)

p <- ggplot(pd, aes(x=k, y=value, linetype=variable))
pq <- p + geom_line() + geom_point(aes(shape=variable),
                                   fill="white", shape=21, size=1.40) +
  geom_errorbar(aes(ymax=value+sd, ymin=value-sd), width=4) +
  scale_y_continuous("Ratio wrt worst value") +
  scale_x_continuous("Number of topics",
                     breaks=K) +
  theme_bw()
pq




# ****** Visualizing the topics ******* 


library(tidytext)
library(dplyr)
library(stringr)
library(ggplot2)
library(plotly)

# Planned Parenthood, 1
# Mike Pence, 2
# White House, 13
# Supreme Court, 17
# Clinton, 19
# Women's March, 26
# Health Care, 28
# Betsy DeVos, 31
# Dakota Access, 34
# Obama, 36
# Meryl Streep, 38
# Police, 39
# Immigration, 44
# Trump, 48

top500topics <- read.csv("top500with50predictedtopicsnew.csv", stringsAsFactors = FALSE)

# Visualize topics across time

tab1 <- table(top500topics$Date[top500topics$pred_topic==1])
plot(tab1, lwd = 2, ylab = "Planned Parenthood articles")
tab2 <- table(top500topics$Date[top500topics$pred_topic==2])
plot(tab2, lwd = 2, ylab = "Mike Pence articles")
tab13 <- table(top500topics$Date[top500topics$pred_topic==13])
plot(tab13, lwd = 2, ylab = "White House articles")
tab17 <- table(top500topics$Date[top500topics$pred_topic==17])
plot(tab17, lwd = 2, ylab = "Supreme Court articles")
tab19 <- table(top500topics$Date[top500topics$pred_topic==19])
plot(tab19, lwd = 2, ylab = "Clinton articles")
tab26 <- table(top500topics$Date[top500topics$pred_topic==26])
plot(tab26, lwd = 2, ylab = "Women's March articles")
tab28 <- table(top500topics$Date[top500topics$pred_topic==28])
plot(tab28, lwd = 2, ylab = "Health Care articles")
tab31 <- table(top500topics$Date[top500topics$pred_topic==31])
plot(tab31, lwd = 2, ylab = "Betsy DeVos articles")
tab34 <- table(top500topics$Date[top500topics$pred_topic==34])
plot(tab34, lwd = 2, ylab = "Dakota Access articles")
tab36 <- table(top500topics$Date[top500topics$pred_topic==36])
plot(tab36, lwd = 2, ylab = "Obama articles")
tab38 <- table(top500topics$Date[top500topics$pred_topic==38])
plot(tab38, lwd = 2, ylab = "Meryl Streep articles")
tab39 <- table(top500topics$Date[top500topics$pred_topic==39])
plot(tab39, lwd = 2, ylab = "Police articles")
tab44 <- table(top500topics$Date[top500topics$pred_topic==44])
plot(tab44, lwd = 2, ylab = "Immigration articles")
tab48 <- table(top500topics$Date[top500topics$pred_topic==48])
plot(tab48, lwd = 2, ylab = "Trump articles")

# Build heatmap of pivot table

heatmap <- read.csv("topicsheatmap.csv")
View(heatmap)
library(ggplot2)
row.names(heatmap) <- heatmap$outlet
heatmap$outlet  <- NULL
heatmap$Total <- NULL
heatmap_matrix <- data.matrix(heatmap)
library(RColorBrewer)
topics_heatmap <- heatmap(heatmap_matrix, Rowv=NA, Colv=NA, col = cm.colors(256), scale="column", margins=c(5,10))

# Build barplot of topics by social shares

library(plotly)
socialshares <- read.csv("8topicssocialshares.csv")
View(socialshares)
psocial <- plot_ly(socialshares, x = ~topic_name, y = ~total_facebook, type = 'bar', name = 'Facebook') %>%
  add_trace(y = ~total_twitter, name = 'Twitter') %>%
  layout(title = "Social shares by topic Nov 2016 - May 2017",
         xaxis = list(title = "", tickangle = -45),
         yaxis = list(title = "Social shares"),
         margin = list(b = 100),
         barmode = 'group')

psocial


```
