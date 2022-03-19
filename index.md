# **Meme information**
*So...You'd like to know more about my meme..?!*
.

## In this section you will be able to find...
* The R code used to produce my meme
* What the motivation was behind the meme
* How my meme is new/original 

## **R code**

```r
library(magick)

#top panel 
top_panel <- image_blank(width = 800,
            height = 200,
            color = "#f2f2f2") %>%
  image_annotate(text = "One taught me patience \n \nOne taught me pain",
                 color = "#00091a",
                 size = 40,
                 font = "Ptsansnarrow",
                 weight = 200,
                 location = geometry_point(50,20))

#Left image
code_academy <- image_read("https://images.codecademy.com/social/logo-codecademy-social.png")%>%
  image_scale (500)


#right image
r_logo <- image_read("https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQzkxgNUbsmMULPBNUGxbrhJQvs3YFg_ZP9ssmJQxJSerMZAT7pf1h5pRf39_W3rfMkQCc&usqp=CAU") %>%
  image_scale (300)


#append logos
logo_vector <-c(code_academy, r_logo)
bottom_row <-image_append(logo_vector)

#making the whole thing 
meme <- c(top_panel,bottom_row) %>%
  image_append(stack = TRUE)

meme

image_write(meme, "my_meme.png")
```

## **What was the motivation behind this meme?** 
The main motivation behind this meme was to make something that was fun, and relevant to the stats220 course. 
The meme explores the early struggles of a new coder who is overwhelmed by learning to code with R. 
This was a fun method of venting frustrations in a constructive manner (with the pleasure of Ariana's 'Thank you, next,' in my head for the rest of the day).  

## **How is this meme new/original?**
This meme uses a simple and popular meme format, depicting two images that relate the song lyrics 'one taught me patience,' and 'one taught me pain.'
My meme adapts this format and utilises relatable content for new coders. 
