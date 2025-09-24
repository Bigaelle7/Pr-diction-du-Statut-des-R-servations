# Projet : Prédiction des Annulations de Réservations

## Contexte
Une entreprise de transport subit des pertes à cause des réservations annulées ou incomplètes.  
L’objectif de ce projet est de **prédire si une réservation sera complétée ou annulée**, afin de réduire les pertes et améliorer l’expérience client et chauffeur.



## Dataset
Le dataset contient des informations sur les réservations :  
- Type de véhicule (`Vehicle Type`)  
- Distance du trajet (`Ride Distance`)  
- Montant de la réservation (`Booking Value`)  
- Notes du client et du chauffeur (`avg ctat`, `avg vtat`)  
- Méthode de paiement (`Payment Method`)  
- Jour et heure de réservation (`Booking Day`, `Booking Hour`)  
- Raison d’annulation pour clients et chauffeurs  

**Prétraitement effectué :**  
- Nettoyage des valeurs manquantes (`NaN`)  
- Encodage des variables catégorielles avec `LabelEncoder`  
- Création de la cible binaire :  
  - `Completed` = 1  
  - `Cancelled`, `Incomplete`, `No Driver Found` = 0  


## Méthodologie

1. **Exploration des données (EDA)**  
   - Visualisation de la distribution des statuts de réservation  
   - Analyse des patterns selon type de véhicule, jour, distance et méthode de paiement  
   - Corrélations entre variables  

2. **Modélisation supervisée**  
   - Séparation des données en `train` et `test`  
   - Modèles utilisés :  
     - **Forêt Aléatoire (Random Forest)**  
     - **XGBoost**  
   - Évaluation avec : Accuracy, Precision, Recall, F1-score, AUC  

3. **Interprétation avec SHAP**  
   - Identification des features les plus importantes pour le modèle  
   - Visualisation avec bar plot (importance globale) et dot plot (impact directionnel)  


## Résultats clés

- Les **6 features les plus importantes** selon SHAP :  
  1. `Payment Method`  
  2. `Rides incomplètes (Incomplete Rides)`  
  3. `Ride Distance`  
  4. `Booking Value`  
  5. `avg ctat` (Customer Rating)  
  6. `avg vtat` (Driver Rating)  

- **Performance des modèles :**  
  | Modèle | Accuracy | Precision | Recall | F1-score | AUC |
  |--------|---------|----------|--------|----------|-----|
  | Random Forest | 0.XX | 0.XX | 0.XX | 0.XX | 0.XX |
  | XGBoost | 0.XX | 0.XX | 0.XX | 0.XX | 0.XX |

- Les deux modèles prédisent efficacement les réservations à risque d’annulation. XGBoost est légèrement plus performant, mais la Forêt Aléatoire reste compétitive et plus simple à interpréter.


## Conclusions

- Le modèle permet d’**anticiper les annulations** et d’identifier les facteurs qui influencent le statut des réservations.  
- Les features clés offrent des **insights actionnables pour le business**.  


## Recommandations business

1. **Optimiser la méthode de paiement** pour réduire les annulations.  
2. **Réduire les courses incomplètes avec des pénalités douces ou des récompenses de fidélité..**  
3. **Surveiller les trajets longs ou coûteux** pour anticiper les risques.  
4. **Suivi des notes clients et chauffeurs** pour améliorer la fiabilité des courses.  
5. **Mise à jour régulière du modèle** avec les nouvelles données pour maintenir sa performance.

## Auteur
**Bigaëlle Guerrier**  


