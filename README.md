<h1 align="center"> Endemic Gastropods Data Analysis </h1>

## File Organization 

```
 📦STAT387_FinalProject      
 ┣ 📂lib                                        // Supplementary materials
 ┃ ┣ 📄AGENDA.md                                // Current project objectives 
 ┃ ┣ 📄Johnston_and_Cohen_1986_Palaios.pdf      // Data context source
 ┃ ┣ 📄notes.txt                                // Potential inquiry goals
 ┃ ┣ 📄variable_definitions.png                 // Variable source definitions
 ┃ ┗ 📄variable_definitions2.png                // Expanded variable source definitions
 ┣ 📂src                                        // Source code
 ┃ ┣ 📂data                                     // Source Data 
 ┃ ┃ ┣ 📂raw                                    // Preprocessed data
 ┃ ┃ ┃ ┗ 📄snail.csv                            // Original data
 ┃ ┃ ┗ 📂processed                              // Analyzed data
 ┃ ┃   ┣ 📄snail.RData                          // Re-formatted original data 
 ┃ ┃   ┣ 📄snail1.RData                         // `Type1` data from `ShellType` variable 
 ┃ ┃   ┗ 📄snail2.RData                         // `Type2` data from `ShellType` variable 
 ┃ ┣ 📂exploration.Rmd                          // Exploratory data analysis code            
 ┃ ┣ 📂exp_snails1.Rmd                          // `Type1` Exploratory data analysis code
 ┃ ┣ 📂exp_snails2.Rmd                          // `Type2` Exploratory data analysis code
 ┃ ┣ 📄FinalPaper.Rmd                           // RMarkdown file to create final paper
 ┃ ┣ 📄Complete_Code.R                          // Instructor desired R script 
 ┃ ┗ 📄outputs                                  // Visualizations
 ┃   ┣ 📂figures                                // Infographics
 ┃   ┣ 📂FinalPaper.pdf                         // RMarkdown final paper output
 ┃   ┣ 📂FinalPresentation                      // Slides for presentation
 ┃   ┗ 📂plots                                  // Graphs
 ┣ 📄.gitignore                                 
 ┗ 📄README.md
```
---

## Preamble:
Consider the snail data available in the `Snail2.csv`. Take Length as the response variable and we would like to understand how it is related with other variables in the data.

## Problem statements:

<ol type="a">
  <li> Perform an exploratory analysis of data.</li>
  
  <li> Is Length appropriate as a response variable or a transformation is necessary? In case a transformation of response is necessary, try the natural log transformation or some other simple transformation and use it for the rest of this problem. </li>
  
  <li> Do part (a) of Exercise 15 in Chapter 3 for these data. </li>
  
  <li> Do part (b) of Exercise 15 in Chapter 3 for these data. </li>
  
  <li> Build a reasonably “good” multiple regression model for these data. Be sure to explore interactions of ShellType with other predictors. Carefully justify all the choices you make in building the model and verify the model assumptions. </li>
  
  <li> Write the final model in equation form, being careful to handle qualitative predictors and interactions (if any) properly.</li>
  
  <li> Use the final model to predict the Length of a Type1 snail with other predictors set equal to their sample means. Also provide a 95% prediction interval for the response and a 95% confidence interval for the mean response. Repeat for a Type2 snail, and compare the answers. </li>
</ol>

---

## Data Variables:

|   Variable    |               Definition                |
|:-------------:|:---------------------------------------:|
|  `ShellType`  |   Type of shell                         |
|   `Width`     |   Width of the shell                    |
|   `Length`    |   Length of the shell                   |
|   `AperHt`    |   Apertural Height                      |
|   `AperWdt`   |   Apertural Width                       |
|   `LU`        |   Unknown                               |
|   `LipWdt`    |   Measures the apertural lip thickness  |

---

## Source Paper Abstract

Patterns of variability in gastropod shell morphology were used to examine modes of morphological divergence and their implications for intra-lacustrine divergence. Two Thiaridae gastropods endemic to Lake Tanganyika, that are both stenotopic and rock-dwelling, were investigated because they are believed to be equally subject to environmental barriers to dispersal. A model of Allopatric speciation divergence, facilitated by habitat fragmentation, predicts that variation among populations should be large relative to the variation within them, and that organisms equally subject to environmental barriers to dispersal should exhibit similar magnitude and character of morphological divergence. Spekia and members of the Lavigeria species flock appear only in rocky, wave-battered shoals and neither gastropod is known to exhibit wide dispersal. Intervening reaches of sandy and muddy substrates are thought to be barriers to gene flow. Analyses of variance of factor scores reveal that interpopulation morphological variance is greater than intrapopulation variance for both genera, suggesting that divergence is allopatric. However, Spekia shows little morphological variability compared to shallow-water Lavigeria. In graphical analyses of factor scores, Lavigeria forms discrete clusters of morphology related to differences in environment, geographic distribution, and timing of larval broods, all indicative of speciation. The model of allopatric divergence controlled by environmental barriers to dispersal must be reviewed because of two incongruent results: sympatry of divergent morphs of Lavigeria, and the observation that members of Lavigeria show much greater endemic divergence than members of Spekia, even though they are thought to be equally poor dispersers.

**Source:** [PALAIOS (1987) 2 (5): 413–425](https://doi.org/10.2307/3514613)