# Web_scraping

## Mini Project 01 - IMDB we scraping
library(tidyverse)
library(rvest)

url <- "https://www.imdb.com/search/title/?groups=top_100&sort=user_rating,desc"
imdb <- read_html(url)

# movie title
titles <- imdb %>%
    html_nodes("h3.lister-item-header") %>%
    html_text2()
titles[1:10]

# rating
ratings <- imdb %>%
    html_nodes("div.ratings-imdb-rating") %>%
    html_text2() %>%
    as.numeric() # covert factor to numeric

# votes
num_votes <- imdb %>%
    html_nodes("p.sort-num_votes-visible") %>%
    html_text2()

# build a dataset
df <- data.frame(
    Title = titles,
    Rating = ratings,
    Vote = num_votes
)
head(df)
