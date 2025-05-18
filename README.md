# Avaluació de l'Heterogeneïtat de l'Efecte del Tractament en Assaigs Clínics

Aquest repositori conté el codi en llenguatge R desenvolupat per a l'estudi del Treball de Fi de Màster titulat **"Avaluació de l'Heterogeneïtat de l'Efecte del Tractament en Assaigs Clínics"** realitzat per **Carla Iranzo Aixalà** al Màster Interuniversitari en Estadística i Investigació Operativa (UPC-UB).

## Objectiu del projecte

L'objectiu principal és comparar diferents mètodes estadístics per estimar l'efecte individual del tractament (PITE) en assaigs clínics aleatoritzats, i així avaluar la seva **heterogeneïtat**. Aquest enfocament permet millorar la medicina personalitzada, ajustant els tractaments a cada pacient.

## Contingut del codi

L'script `.Rmd` inclòs implementa i compara quatre mètodes per estimar el PITE:

1. *Imputació múltiple paramètrica*  
2. *Arbres de decisió (RDT)*
3. *Boscos aleatoris*
4. *Boscos causals*

##  Simulacions

Per avaluar la capacitat dels diferents mètodes d’estimar l’efecte individual del tractament (PITE), es van definir tres escenaris de simulació que reprodueixen diferents tipus d’heterogeneïtat en l’efecte del tractament. Tots els escenaris es basen en covariables generades amb estructura realista a partir de dades d’un assaig clínic real.

Escenari 1: Efecte constant
- Descripció: L’efecte del tractament és el mateix per a tots els individus.
- SITE (Simulated Individual Treatment Effect): constant per a tots els pacients.

Escenari 2: Efecte dependent de covariables
- Descripció: L’efecte del tractament varia segons les covariables individuals.
- SITE: es calcula com una combinació lineal de les covariables.

Escenari 3: Efecte aleatori
- Descripció: L’efecte del tractament és diferent per a cada individu, però no està relacionat amb cap covariable.
- SITE: generat aleatòriament per a cada individu seguint una distribució normal.

Paràmetres comuns
- Cada simulació es repeteix 100 vegades per garantir robustesa estadística.
- Es mesura el ràtio entre la variància estimada del PITE i la variància real del SITE per avaluar el rendiment de cada mètode.

## Dades

Les simulacions utilitzen paràmetres i distribucions basades en un conjunt de dades reals de 543 pacients, on es recullen variables com:

- **Tractament**: Grup d’intervenció (IV vs. IM)
- **Resposta**: Quantitat total de sang perduda (ml)
- **Covariables**: `antibioticos`, `episiotomia`, `masajeuterino`, `sutura`, `HBdrop2ormore`, `uterotonicos`, `hpp`, `indoraug`, entre d'altres.

## Paquets R utilitzats

El codi fa ús dels següents paquets R:

- `tidyverse`, `dplyr`, `tidyr`, `ggplot2`
- `mice`, `rpart`, `randomForest`, `grf`
- `lme4`, `truncnorm`, `patchwork`

## Execució

El fitxer `.Rmd` està pensat per ser executat a RStudio. Inclou tant la generació de dades simulades com l'aplicació dels mètodes als diferents escenaris, així com la creació de gràfics i taules.

## Resultats esperats

Els resultats permeten comparar el rendiment dels mètodes en termes de precisió, robustesa i sensibilitat a informació no rellevant (variables soroll). També s’avalua la seva aplicabilitat a situacions reals.

## Autoria

- **Autor**: Carla Iranzo Aixalà  
- **Directors**: Jordi Cortés Martínez, José Antonio González Alastrue  
- **Universitat**: UPC-UB  
- **Data**: Maig 2025
