Pre-class 1 Exercises
---------------------

The warm-up for class will use the mtcars dataset which is always present in R. The following code shows you how load the dataset

``` r
? mtcars # what are the variables
```

    ## starting httpd help server ... done

``` r
cars <- mtcars %>% rownames_to_column(var = "type") # tranform to tibble
```

This a brief re-introduction to the tidyverse package in R

This is something we went through during 1st semester so you should be able to do it, however if the summer have been to harsh I recommend consulting R for data science chapter 5: <https://r4ds.had.co.nz>

``` r
# Using mutate - convert miles per gallon to liters
cars <- mutate(cars, mpl = mpg*3.78541178)
# Using filter - find all the cars which have more that 4 gears and are automatic
above4gears <- filter(cars, gear > 4)
# Using select - create a column dataframe with only miles pr. gallon, weight and number og gears
dataframe1 <- select(cars, mpg,wt,gear)
# Using arrange - What cars are most fuel efficient? (lowest miles pr. liter/gallon)
arrange(cars,mpl)
```

    ##                   type  mpg cyl  disp  hp drat    wt  qsec vs am gear carb
    ## 1   Cadillac Fleetwood 10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4
    ## 2  Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4
    ## 3           Camaro Z28 13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4
    ## 4           Duster 360 14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4
    ## 5    Chrysler Imperial 14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4
    ## 6        Maserati Bora 15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8
    ## 7          Merc 450SLC 15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3
    ## 8          AMC Javelin 15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2
    ## 9     Dodge Challenger 15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2
    ## 10      Ford Pantera L 15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4
    ## 11          Merc 450SE 16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3
    ## 12          Merc 450SL 17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3
    ## 13           Merc 280C 17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4
    ## 14             Valiant 18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1
    ## 15   Hornet Sportabout 18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2
    ## 16            Merc 280 19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4
    ## 17    Pontiac Firebird 19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2
    ## 18        Ferrari Dino 19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6
    ## 19           Mazda RX4 21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4
    ## 20       Mazda RX4 Wag 21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4
    ## 21      Hornet 4 Drive 21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1
    ## 22          Volvo 142E 21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2
    ## 23       Toyota Corona 21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1
    ## 24          Datsun 710 22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1
    ## 25            Merc 230 22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2
    ## 26           Merc 240D 24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2
    ## 27       Porsche 914-2 26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2
    ## 28           Fiat X1-9 27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1
    ## 29         Honda Civic 30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2
    ## 30        Lotus Europa 30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2
    ## 31            Fiat 128 32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1
    ## 32      Toyota Corolla 33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1
    ##          mpl
    ## 1   39.36828
    ## 2   39.36828
    ## 3   50.34598
    ## 4   54.13139
    ## 5   55.64555
    ## 6   56.78118
    ## 7   57.53826
    ## 8   57.53826
    ## 9   58.67388
    ## 10  59.80951
    ## 11  62.08075
    ## 12  65.48762
    ## 13  67.38033
    ## 14  68.51595
    ## 15  70.78720
    ## 16  72.67991
    ## 17  72.67991
    ## 18  74.57261
    ## 19  79.49365
    ## 20  79.49365
    ## 21  81.00781
    ## 22  81.00781
    ## 23  81.38635
    ## 24  86.30739
    ## 25  86.30739
    ## 26  92.36405
    ## 27  98.42071
    ## 28 103.34174
    ## 29 115.07652
    ## 30 115.07652
    ## 31 122.64734
    ## 32 128.32546

``` r
# Using Group_by and summarise - Find out how many cars have 3 gears, how many have 4 and how many have 5 (tip use n(), with summarise to count number of occurences)
gear_tibble <- cars %>% 
  group_by(gear) %>% 
  summarise(count=n())
# If you haven't yet, solve the above task using pipe, they look like this '%>%' and can be read as 'then' e.g. the following lines:
mtcars %>% 
  mutate(number = 200) %>% 
  summarise(sum_num = sum(number)) %>% 
  mutate(n_row = sum_num / 200)
```

    ##   sum_num n_row
    ## 1    6400    32

``` r
# can be read as 'take mtcars, 
  # THEN add a column called numbers which is equal to 200
  # THEN the summarise the using the sum of numbers 
  # THEN divide the sum of the number by 200 to get the number of rows

#create some sort of plot plotting the data
plot <- ggplot(gear_tibble, aes(gear, count))+
  geom_bar(stat = "summary", fun.y = mean, aes(fill=gear))+
  theme(legend.position = "none")
plot
```

![](pre_class_1_exercises_files/figure-markdown_github/unnamed-chunk-1-1.png)
