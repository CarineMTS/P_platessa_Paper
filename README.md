# P_platessa_Paper

## Introduction
  
The following repository is composed of the script with the analyses used in the adjoined journal article: **Sexual maturity determination for the female European plaice, Pleuronectes platessa (Linnaeus, 1758), through quantitative histology**, as well as the data frames used for these analyses. Two main scripts are available.
The first script deals with maturity determination and uses the data on macroscopic measurements and stereological cellular counts. 
The second script is supplementary data that deals with the analyses of the reading calibration exercise data, as well as the inter and intra gonad homogeneity check. 

 ## Supplementary data script

### Inter-agent calibration
For the inter-agent calibration, three reading agents read the same 15 to 20 histological slides, with one agent having read 15 slides, and the other two having read 20 slides. The goal of this exercise was to show the presence or absence of a bias between readings from different operators.

The dataframe **Interagent.csv** contains the readings of the 20 histological slides from the different reading agents:
- **agent** : Reading operator. There are three agents that did the calibration exercise: A, B and C
- **fish id** : Identification number given to each fish during the sampling process
- **num_fish** : number of the fish. Given to simplify from the fish_id. All 151 specimens have a unique number
- **scan_id** : Identification number of the scanned histological side
- **total_points** : Total number of sampling points counted during the stereological analysis on the histological slide. Each sampling grid was composed of 500 to 600 points
- **cell_type** : Abbreviations of name for the counted cellular structure
- **hit_points** : Number of times a structure was counted for the matching slide
- **fract_estim** : Counted percentage (%) of the cellular structure for the matching slide
- **reading** : Number of the reading exercise. Here we did 2 reading exercises (1 and 2)

### Cellular homogeneity check
For the cellular homogeneity check, the two ovaries of 15 fish were sectioned in the anterior, posterior and median positions. Cellular counts were analyzed and compared.

The dataframe **Stereology.csv** contains the data of those readings (**homogeneity** factor in the **reading** column). Stats on the counted surface values found by 3 readers :
- **minsurf %** : minimum value, for the counted cellular structure (%), found between the 3 reading agents
- **maxsurf %** : maximum value, for the counted cellular structure (%), found between the 3 reading agents
- **diffperc %** : diffrence between the min (minsurf) and the max (maxsurf) values
- **sdperc %** : standard deviation for the min and max values found between the reading agents
- **meanperc %** : mean of the min and max values found between the reading agents
- **CV %** : Coefficient of Variation, no unit, expressed in %.
- **medianeperc %** : median value (%) of the counted cellular structures
- **madperc %** : Mean Absolute Deviation of the counted cellular structures (%).

## Maturity analyses data script

Stereological counts (quantified by the number of cells, in percentage, counted on a sampling grid covering the entire ovarian histological slide) helps link a maturity phase to each individuals (following the definitions of the ICES (WKMATCH, WKASMSF) and Brown-Peterson et al. (2011)). These phases are then linked with the plaice's macroscopic parameters. The results from the stereological method were also compared to the results from the visual maturity determination method. 

### Macroscopic parameters
Macroscopic parameters were collected for all 151 female plaice. Only the ventral ("V") ovaries are taken into consideration. List of measured parameters :
- **L_fish**: total lengh of fish (cm)
- **W_fish**: ungetted weight of fish (g)
- **mat_estim**: visually estimated maturity phase
- **age**: fish age (year)
- **W_gon**: weight of the ovary (g)
- **gon_area**: surface area of the ovary (mm??)
- **L_gon**: length of the ovary (mm)
- **Width_gon**: width of the ovary (mm)
- **Width_mid_L_gon**: max width at mid-length of the ovary (mm)
- **mean_col_index**: mean color of the ovary (index between 0 and 360)
- **modal**: median color of the ovary (index between 0 and 360)
- **rap**: ratio between the ovary's length and the fish's total length
- **rapgon**: ratio between the ovary's weight and its length
- **rapgonw**: ratio between the ovary's weight and the fish's ungutter weight (gonado-somatic index)

### Histological structures
20 cellular structures have been identified throughout the 151 sampled ovarian slides :
- **ov**: oogonium
- **op1**: premature stage 1 oocyte
- **op2**: premature stage 2 oocyte
- **oca**: cortical alveoli oocyte
- **vit1**: oocyte in early vitellogenesis
- **vit2**: oocyte in vitellogenesis with nucleus migration
- **vit3**: oocyte in vitellogenesis with zona pellucida growth
- **vit4**: oocyte at the end of vitellogenesis
- **och**: oocyte in hydration
- **oh**: hydrated oocyte
- **POF**: post-Ovulatory Follicle
- **oaA**: oocyte in alpha atresia
- **oaB**: oocyte in beta atresia
- **L**: lysis
- **ei**: intercellular space
- **i**: undetermined
- **pg**: gonadal wall
- **tc**: connective tissue
- **v**: unatural emptiness
- **cs**: blood vessel

### Manual determination of the maturity phases

Following the ICES and Brown-Peterson et al. (2011) definitions, the stereological counts were used to classify each individual into a maturity phase. For this process, only the phases A, B, C and E were established, with all remaining slides being automatically put into the D (Regressing/Regenerating) phase.

#### Immature - A
Individuals classified into the Immature phase have the following histological criteria:
- a count of **ov**, **op1** or **op2** that is not null
- absence of **POF**, **oca**, **vit1**, **vit2**, **vit3**, **vit4**, **och** and **oh**

#### Developing - B
Individuals classified into the Developing phase have the following histological criteria:
- presence of either **oca**, **vit1**, **vit2** or **vit3**
- a count of **oaA** of less than or equal to 50% of the total follicles quantified
- absence of **POF**, **oaB**, **vit4**,  **och** and **oh**

#### Spawning - C
Individuals classified into the Spawning phase have the following histological criteria:

Beginning of phase :
- absence of **POF** and of **oaB**
- presence of either **vit4**, **och** or **oh**
- a count of **oaA** of less than or equal to 50% of the total follicles quantified

End of phase :
- absence of **oaB**
- presence of either **vit4**, **och** or **oh**
- a count of **oaA** of less than or equal to 50% of the total follicles quantified
- presence of **POF** that does not exceed the number of **oh**

#### Omitted Spawning - E
Individuals classified into the Omitted Spawning phase have the following histological criteria:
- a count of **oaA** of more than 50% of the total oocytes quantified
- absence of **POF**

#### Regressing / Regenerating - D
Individuals classified into the Regressing/Regenerating phase are those that have not been classified into the other phases.
