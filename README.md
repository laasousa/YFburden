
<!-- README.md is generated from README.Rmd. Please edit that file -->
YFburden
========

The goal of YFburden is to calculate the number of cases, deaths and DALYs of yellow fever in Africa. It takes estimates of the transmission intensity and inputs such as vaccination coverage, population size and life expectancy to calculate the number of infections and thus burden.

Installation
------------

You can install YFburden from github with:

``` r
# install.packages("drat")
drat:::add("mrc-ide")
install.packages("YFburden")
```

Example
-------

``` r
#historic_dat = vaccination campaigns before 2000 (pre-GAVI)

#GAVI_preventative = GAVI projected vaccination activities FROM MONTAGU

#GAVI_switch = "routine", "no-vaccination", "preventive"

#param_samples = a vector of transmission intensities across the region

#pop_all = population size by year, age and country FROM MONTAGU

#P_severe = probability of a severe yellow fever infection

#P_severeDeath = probability that an individual with severe yellow fever dies

#life_exp_GAVI = life expectancies by year, age and countries  FROM MONTAGU

#template = output template FROM MONTAGU

#round = whether to round or not

#run_id = parameter sample number, for stochastic runs only

output_df = run_burden_for_template(historic_dat,
                                    GAVI_preventive,
                                    GAVI_switch,
                                    param_samples,
                                    pop_all,
                                    P_severe,
                                    P_severeDeath,
                                    life_exp_GAVI,
                                    template,
                                    round = TRUE,
                                    run_id = NA)
```

Then `output_df` would look something like this:

| disease |  year|  age| country | country\_name |  cohort\_size|  deaths|  cases|  dalys|
|:--------|-----:|----:|:--------|:--------------|-------------:|-------:|------:|------:|
| YF      |  2000|    0| AGO     | Angola        |        700752|      13|     27|    715|
