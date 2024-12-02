
# README: Étapes pour réaliser QDA, LDA et Naive Bayes from scratch

Ce document décrit les étapes détaillées pour implémenter les modèles QDA, LDA et Naive Bayes à partir de zéro.

---

## 1. Quadratic Discriminant Analysis (QDA)

### Étapes d'implémentation :
1. **Initialisation des paramètres :**
   - Identifier les classes uniques dans les données d'entraînement.
   - Calculer les probabilities a priori pour chaque classe.

2. **Calcul des statistiques pour chaque classe :**
   - Moyenne (μ) : Calculer la moyenne de chaque classe pour chaque caractéristique.
   - Covariance (Σ) : Calculer la matrice de covariance pour chaque classe.

3. **Fonction de densité gaussienne :**
   - Implémenter la fonction multivariée normale pour calculer la probabilité de densité pour un point donné.

4. **Prédiction :**
   - Pour chaque point, calculer la probabilité a posteriori pour chaque classe en multipliant la densité gaussienne par la probabilité a priori.
   - Prédire la classe avec la probabilité a posteriori maximale.

5. **Gestion des erreurs possibles :**
   - Vérifier si les matrices de covariance sont singulières et gérer les inversions.

---

## 2. Linear Discriminant Analysis (LDA)

### Étapes d'implémentation :
1. **Initialisation des paramètres :**
   - Identifier les classes uniques dans les données.
   - Calculer les probabilities a priori pour chaque classe.

2. **Calcul des statistiques globales et par classe :**
   - Moyenne par classe : Moyenne des données appartenant à chaque classe.
   - Matrice de covariance partagée (Σ) : Moyenne pondérée des matrices de covariance par classe.

3. **Calcul des coefficients pour les frontières de décision :**
   - Calculer la matrice inversée de la covariance partagée.
   - Implémenter la formule pour les frontières de décision linéaires.

4. **Prédiction :**
   - Pour chaque point, calculer la fonction discriminante linéaire pour chaque classe.
   - Prédire la classe avec le score discriminant le plus élevé.

5. **Validation des hypothèses :**
   - Vérifier que les matrices de covariance par classe sont similaires pour utiliser LDA correctement.

---

## 3. Naive Bayes

### Étapes d'implémentation :
1. **Initialisation des paramètres :**
   - Identifier les classes uniques dans les données.
   - Calculer les probabilities a priori pour chaque classe.

2. **Estimation des paramètres par caractéristique :**
   - Moyenne (μ) et variances ( $σ^2$ ) pour chaque caractéristique de chaque classe.
   - Assumer l'indépendance conditionnelle entre les caractéristiques.

3. **Calcul des probabilités conditionnelles :**
   - Implémenter la fonction de densité gaussienne pour chaque caractéristique.

4. **Prédiction :**
   - Calculer la probabilité a posteriori pour chaque classe comme le produit des probabilités conditionnelles des caractéristiques et des prior probabilities.
   - Prédire la classe avec la probabilité a posteriori maximale.

5. **Validation et ajustement :**
   - Vérifier l'indépendance approximative entre les caractéristiques.
   - Gérer les caractéristiques catégoriques si elles sont présentes (optionnel).

---

## Différences dans l'implémentation :

| Critères               | QDA                           | LDA                           | Naive Bayes                 |
|------------------------|-------------------------------|-------------------------------|-----------------------------|
| Hypothèse sur covariance | Covariance par classe        | Covariance partagée           | Pas de covariance utilisée  |
| Calcul de la probabilité | Multivariée normale          | Multivariée normale           | Produit des densités univariées |
| Complexité             | Haute                        | Moyenne                       | Basse                        |

---

## Conclusion :
Ces modèles illustrent différentes approches bayésiennes pour la classification. QDA est plus flexible mais coûteux, LDA est linéairement rapide et utile pour réduire la dimensionnalité, tandis que Naive Bayes est idéal pour des applications où l'indépendance conditionnelle est approximativement vraie.

---

## Références pour l'implémentation :
1. Cours théoriques sur les modèles bayésiens.
2. Ouvrages de référence : "The Elements of Statistical Learning".
3. Tutoriels de mise en œuvre en Python.
