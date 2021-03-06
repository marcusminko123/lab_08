Lab 08 - Conveying the right message through visualisation
================
Marcus Minko
02-23-2022

### Load packages and data

``` r
library(tidyverse) 
```

### Create Dataframe

``` r
mask_mandates <- tribble(
  ~date, ~count, ~mandate,
  "7/13/2020", 22.5, "YES",
  "7/13/2020", 9.5, "NO",
  "7/14/2020", 19.8, "YES",
  "7/14/2020", 9.4, "NO",
  "7/15/2020", 20, "YES",
  "7/15/2020", 9.8, "NO",
  "7/16/2020", 19.8, "YES",
  "7/16/2020", 9.9, "NO",
  "7/17/2020", 19.6, "YES",
  "7/17/2020", 9.8, "NO",
  "7/18/2020", 20, "YES",
  "7/18/2020", 9.5, "NO",
  "7/19/2020", 20.2, "YES",
  "7/19/2020", 9.3, "NO",
  "7/20/2020", 20.3, "YES",
  "7/20/2020", 8.7, "NO",
  "7/21/2020", 21.1, "YES",
  "7/21/2020", 8.6, "NO",
  "7/22/2020", 21.3, "YES",
  "7/22/2020", 8.8, "NO",
  "7/23/2020", 20, "YES",
  "7/23/2020", 8.6, "NO",
  "7/24/2020", 20.1, "YES",
  "7/24/2020", 9.1, "NO",
  "7/25/2020", 20, "YES",
  "7/25/2020", 9.9, "NO",
  "7/26/2020", 19.1, "YES",
  "7/26/2020", 10, "NO",
  "7/27/2020", 19.6, "YES",
  "7/27/2020", 9.8, "NO",
  "7/28/2020", 16.9, "YES",
  "7/28/2020", 9.4, "NO",
  "7/29/2020", 16.7, "YES",
  "7/29/2020", 9.7, "NO",
  "7/30/2020", 16.7, "YES",
  "7/30/2020", 9.9, "NO",
  "7/31/2020", 16.4, "YES",
  "7/31/2020", 9.7, "NO",
  "8/1/2020", 16.2, "YES",
  "8/1/2020", 9, "NO",
  "8/2/2020", 15.9, "YES",
  "8/2/2020", 8.8, "NO",
  "8/3/2020", 15.8, "YES",
  "8/3/2020", 8.7, "NO"
  
)
```

### Revizualize

``` r
mask_mandates %>% 
      ggplot(aes
             (x = date, 
              y = count, 
              color = mandate, 
              group = mandate)) + 
                  geom_line(
                         size = 2) + 
                         theme_minimal() + 
                         theme(axis.text.x = element_text(angle = 45, hjust = 1)) +
                         scale_colour_viridis_d() +
  labs(
            title = "Effect of mask mandates on COVID-19 case", 
            subtitle = "July 13 - Aug 3, 2020", 
            x = "Date", y = "Case Count", col = "Mask Mandate") 
```

![](lab-08_files/figure-gfm/reviz-1.png)<!-- -->

This new visualization corrects the issue of two different scales
imposed on one another, which was confusing and misleading. Here you can
easily see that case counts are much lower in non-mask mandate areas.
You can also see that cases were going down where mandates were in
place.

The takeaways appear to be that a lack of a mask mandate does not appear
to lead to a rise in cases, but it does appear to lead to a decline.
Nothing here should be taken as casual as there are likely innumerable
confounds. Though still imperfect, this visualization is far superior to
the original.

???
