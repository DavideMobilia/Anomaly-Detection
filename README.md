# Industry-Lab--Project

Approccio Statistico: ottenere una curva media da cui definire un range di riferimento attraverso cui definire eventuali anomalie della curva
- Calcolo dei valori medi/mediani per ogni istante di saldatura:
  - Per tutti i dati
  - Raggruppati per spotName
  - Raggruppati per istante temporale (ora?)
 - Fittare i punti medi/mediani per ricavarne la curva di riferimento
 - Calcolare range di ammissione per definire inlier/outlier (utlizzando varianza?)
 - Definizione delle anomalie sulla base della distanza dalla curva media
    - Per l'intera curva (MSE?)
    - Puntuali
  
## Considerazioni importanti
Creazione di uno score sulla base della numerosità delle anomalie riscontrate e la loro tipologia
Definizione delle anomalie: sono solo alcuni punti della curva o uno scostamento che ne modificare le caratteristiche

## Criticità
Alcune curve hanno più istanti di saldatura, è un anomalia o un processo diverso?
