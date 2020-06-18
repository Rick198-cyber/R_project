
<!-- README.md is generated from README.Rmd. Please edit that file -->

# palmerpenguins <a href='https://allisonhorst.github.io/palmerpenguins'><img src='man/figures/logo.png' align="right" height="138.5" /></a>

<!-- badges: start -->

<!-- badges: end -->

The goal of palmerpenguins is to provide a great dataset for data
exploration & visualization, as an alternative to `iris`.

## Installation

<!--You can install the released version of palmerpenguins from [CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("palmerpenguins")
```
-->

You can install the development version from
[GitHub](https://github.com/) with:

``` r
# install.packages("remotes")
remotes::install_github("allisonhorst/palmerpenguins")
```

## About the data

Data were collected and made available by [Dr. Kristen
Gorman](https://www.uaf.edu/cfos/people/faculty/detail/kristen-gorman.php)
and the [Palmer Station, Antarctica LTER](https://pal.lternet.edu/), a
member of the [Long Term Ecological Research
Network](https://lternet.edu/).

**Thank you** to Dr. Gorman, Palmer Station LTER and the LTER Network\!
Special thanks to Marty Downs (Director, LTER Network Office) for help
regarding the data license & use.

## License

**Data are available by**
[CC-0](https://creativecommons.org/share-your-work/public-domain/cc0/)
license in accordance with the [Palmer Station LTER Data
Policy](http://pal.lternet.edu/data/policies) and the [LTER Data Access
Policy for Type I data](https://lternet.edu/data-access-policy/).

## Citation

To cite the data used in this package, please use:

``` r
citation("palmerpenguins")
#> 
#> To cite palmerpenguins in publications use:
#> 
#>   Gorman KB, Williams TD, Fraser WR (2014) Ecological Sexual Dimorphism
#>   and Environmental Variability within a Community of Antarctic
#>   Penguins (Genus Pygoscelis). PLoS ONE 9(3): e90081.
#>   https://doi.org/10.1371/journal.pone.0090081
#> 
#> A BibTeX entry for LaTeX users is
#> 
#>   @Article{,
#>     title = {Ecological Sexual Dimorphism and Environmental Variability within a Community of Antarctic Penguins (Genus Pygoscelis)},
#>     author = {Gorman KB and Williams TD and Fraser WR},
#>     journal = {PLoS ONE},
#>     year = {2014},
#>     volume = {9(3)},
#>     number = {e90081},
#>     pages = {-13},
#>     url = {https://doi.org/10.1371/journal.pone.0090081},
#>   }
```

## Example

The palmerpenguins package contains two datasets.

``` r
library(palmerpenguins)
data(package = 'palmerpenguins')
```

One is called `penguins`, and is a simplified version of the raw data.
All column names are in snake case to make them easier to work with, see
`?penguins` for more info:

``` r
head(penguins)
#> # A tibble: 6 x 7
#>   species island bill_length_mm bill_depth_mm flipper_length_… body_mass_g sex  
#>   <fct>   <fct>           <dbl>         <dbl>            <int>       <int> <fct>
#> 1 Adelie  Torge…           39.1          18.7              181        3750 male 
#> 2 Adelie  Torge…           39.5          17.4              186        3800 fema…
#> 3 Adelie  Torge…           40.3          18                195        3250 fema…
#> 4 Adelie  Torge…           NA            NA                 NA          NA <NA> 
#> 5 Adelie  Torge…           36.7          19.3              193        3450 fema…
#> 6 Adelie  Torge…           39.3          20.6              190        3650 male
```

The second dataset is `penguins_raw`, and contains all the variables and
original names as downloaded. See `?penguins_raw` for more info.

``` r
head(penguins_raw)
#> # A tibble: 6 x 17
#>   studyName `Sample Number` Species Region Island Stage `Individual ID`
#>   <chr>               <dbl> <chr>   <chr>  <chr>  <chr> <chr>          
#> 1 PAL0708                 1 Adelie… Anvers Torge… Adul… N1A1           
#> 2 PAL0708                 2 Adelie… Anvers Torge… Adul… N1A2           
#> 3 PAL0708                 3 Adelie… Anvers Torge… Adul… N2A1           
#> 4 PAL0708                 4 Adelie… Anvers Torge… Adul… N2A2           
#> 5 PAL0708                 5 Adelie… Anvers Torge… Adul… N3A1           
#> 6 PAL0708                 6 Adelie… Anvers Torge… Adul… N3A2           
#> # … with 10 more variables: `Clutch Completion` <chr>, `Date Egg` <date>,
#> #   `Culmen Length (mm)` <dbl>, `Culmen Depth (mm)` <dbl>, `Flipper Length
#> #   (mm)` <dbl>, `Body Mass (g)` <dbl>, Sex <chr>, `Delta 15 N (o/oo)` <dbl>,
#> #   `Delta 13 C (o/oo)` <dbl>, Comments <chr>
```

Both datasets contain data for 344 penguins. There are 3 different
species of penguins in this dataset, collected from 3 islands in the
Palmer Archipelago, Antarctica.

``` r
library(tidyverse)
penguins %>% 
  count(species)
#> # A tibble: 3 x 2
#>   species       n
#>   <fct>     <int>
#> 1 Adelie      152
#> 2 Chinstrap    68
#> 3 Gentoo      124
penguins %>% 
  count(island)
#> # A tibble: 3 x 2
#>   island        n
#>   <fct>     <int>
#> 1 Biscoe      168
#> 2 Dream       124
#> 3 Torgersen    52
penguins %>% 
  count(island, species)
#> # A tibble: 5 x 3
#>   island    species       n
#>   <fct>     <fct>     <int>
#> 1 Biscoe    Adelie       44
#> 2 Biscoe    Gentoo      124
#> 3 Dream     Adelie       56
#> 4 Dream     Chinstrap    68
#> 5 Torgersen Adelie       52
```

Penguins are fun to visualize\! For example:

<img src="man/figures/README-mass-flipper-1.png" width="75%" />

You can find more visualizations for exploring palmerpenguins in
`vignette("examples")`.

## Artwork

You can download palmerpenguins art (useful for teaching with the data)
in `vignette("art")`. If you use this artwork, please cite with:
“Artwork by @allison\_horst”.

### Meet the Palmer penguins

<img src="vignettes/articles/img/lter_penguins.png" width="100%" style="display: block; margin: auto;" />

### What are culmen length & depth?

The culmen is the upper ridge of a bird’s bill. In the simplified
`penguins` data, culmen length and depth are renamed as variables
`bill_length_mm` and `bill_depth_mm` to be more intuitive.

For this penguin data, the culmen (bill) length and depth are measured
as shown below (thanks Kristen Gorman for clarifying\!):

<img src="vignettes/articles/img/culmen_depth.png" width="100%" style="display: block; margin: auto;" />

## Additional data use information

Anyone interested in publishing the data should contact [Dr. Kristen
Gorman](https://www.uaf.edu/cfos/people/faculty/detail/kristen-gorman.php)
about analysis and working together on any final products.

From Gorman et al. (2014):

> “Data reported here are publicly available within the PAL-LTER data
> system (datasets \#219, 220, and 221):
> <http://oceaninformatics.ucsd.edu/datazoo/data/pallter/datasets>.
> Individuals interested in using these data are therefore expected to
> follow the US LTER Network’s Data Access Policy, Requirements and Use
> Agreement: <https://lternet.edu/data-access-policy/>.”

**Please cite data using the following:**

**Adélie penguins:**

  - Palmer Station Antarctica LTER and K. Gorman, 2020. Structural size
    measurements and isotopic signatures of foraging among adult male
    and female Adélie penguins (*Pygoscelis adeliae*) nesting along the
    Palmer Archipelago near Palmer Station, 2007-2009 ver 5.
    Environmental Data Initiative.
    <https://doi.org/10.6073/pasta/98b16d7d563f265cb52372c8ca99e60f>
    (Accessed 2020-06-08).

**Gentoo penguins:**

  - Palmer Station Antarctica LTER and K. Gorman, 2020. Structural size
    measurements and isotopic signatures of foraging among adult male
    and female Gentoo penguin (*Pygoscelis papua*) nesting along the
    Palmer Archipelago near Palmer Station, 2007-2009 ver 5.
    Environmental Data Initiative.
    <https://doi.org/10.6073/pasta/7fca67fb28d56ee2ffa3d9370ebda689>
    (Accessed 2020-06-08).

**Chinstrap penguins:**

  - Palmer Station Antarctica LTER and K. Gorman, 2020. Structural size
    measurements and isotopic signatures of foraging among adult male
    and female Chinstrap penguin (*Pygoscelis antarcticus*) nesting
    along the Palmer Archipelago near Palmer Station, 2007-2009 ver 6.
    Environmental Data Initiative.
    <https://doi.org/10.6073/pasta/c14dfcfada8ea13a17536e73eb6fbe9e>
    (Accessed 2020-06-08).

## Contributor Code of Conduct

Please note that the ‘palmerpenguins’ project is released with a
[Contributor Code of Conduct](CODE_OF_CONDUCT.md). By contributing to
this project, you agree to abide by its terms.
