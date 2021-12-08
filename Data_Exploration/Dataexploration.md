# Data Exploration

# Bar Graph
**Different programs offered in each state**

      ![](isqa8600_repo/fig1.png)<!-- -->

```{r}
services.cleaned %>%
  drop_na(program_name) %>%
  ggplot(aes(age, fill = program_name))+
  geom_bar(position = "dodge", alpha = 1)+
  theme_bw()+
  theme(panel.grid.major = element_blank(),
        panel.grid.minor = element_blank())+
         
  labs(x="age",y="Number",
  title = "Different programs offered with each age group")
```
**Analysis**

With my below analysis, the boxplot was performed on combination of categorical and numerical variable and so here I had to analyze different programs that have been offered for each age group and with our result we could see that Mental health program was offered and which is common to all age groups among HFS services.

**Number of age groups present in HFS**

        ![](isqa8600_repo/fig2.png)<!-- -->
        
```{r observationsByAge, echo=TRUE}
services.cleaned %>%
  drop_na(age) %>%
  ggplot(aes(x=age))+
  geom_bar(fill = "#97B3C6")+
  theme_bw()+
  labs(x="age",y=NULL,
       title = "Number of observations per age")
            
```
**Analysis**

Here in this analysis we are observing total number of observations of age records that present in the HFS data, so I considered a single categorical variable, where in x axis is considered to be age. drop_na is used to remove the NA values that are present in the age column.With our analysis we could find that age 25-40 had more number of observations recorded in the HFS data.

# Variable Scatterplots :

**Scatter plot with two variables**
**Event_name and Age**

          ![](isqa8600_repo/fig3.png)<!-- -->

```{r}
ggplot(data = services.cleaned) + geom_point(mapping = aes(x = age, y = event_name))
```
 **Analysis:** 

With my below analysis, the scatterplot was performed on combination of categorical and numerical variable so here I had to analyze different events that have been identified in each age group and most common events that have been common in each age group are Individual Therapy and Admission. Session.


**Age and State**
         ![](isqa8600_repo/fig4.png)<!-- -->
         
```{r}
ggplot(data = services.cleaned) + geom_point(mapping = aes(x = age, y = state))
```         

**Analysis:** 

With my below analysis, the scatterplot was performed on combination of two categorical variable and so here I had to analyze different age groups that have been identified in each state and almost equal amount of age groups have been found common in each state IA(Iowa) and NE(Nebraska).

**Scatter plot with three variables**
**Age, State and is_billable**
            ![](isqa8600_repo/fig5.png)<!-- -->
            
```{r}
ggplot(data = services.cleaned) + geom_point(mapping = aes(x = age, y = state, color = is_billable))
```
**Analysis**

With my below analysis, the scatterplot was performed on combination of two categorical variable and one numerical variable so here I had to analyze different age groups that have been identified in each state and almost it was found that is_billable was found false in each IA (Iowa) and Nebrask (NE). The orange colour depicts "is_billable" to be false.

## Faceted Plot with Two Variables
**Age and State**
          ![](makkamRPlot_files/figure-gfm/avgLikelihoodByRace-1.png)<!-- -->
          
```{r}
ggplot(data = services.cleaned) + geom_point(mapping = aes(x = age, y = state)) + facet_grid(. ~ state)
```          
**Analysis**

With my below analysis, the wanted to try faceted plot as a combination of two categorical variable  so here I had to analyze different age groups that have been identified in each state and almost it was found that is_billable was found false in each IA (Iowa) and Nebrask (NE). The orange colour depicts "is_billable" to be false.

