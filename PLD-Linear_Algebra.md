# 🧠 Fiche de Révision – Algèbre Linéaire et NumPy

## 📚 Sommaire
1. [Concepts de base](#concepts-de-base)
2. [Opérations sur les données](#opérations-sur-les-données)
3. [NumPy et calculs avancés](#numpy-et-calculs-avancés)
4. [Tableau récapitulatif](#tableau-récapitulatif)
5. [Défis pratiques](#défis-pratiques)

---

## 🔷 Concepts de base

### ✅ 1. Vecteur
**Définition :** Un vecteur est une **ligne de nombres** (1D).

**Exemple :**
```python
v = [2, 4, 6]
```

**🎯 À retenir :**
- Représente une **direction + une grandeur** (ex : vitesse, force)
- Visualisation : comme une **flèche** dans l'espace
- Usage pratique : liste de valeurs (notes d'un élève, coordonnées GPS)

---

### ✅ 2. Matrice
**Définition :** Une matrice est un **tableau de nombres** avec lignes et colonnes (2D).

**Exemple :**
```python
M = [[1, 2, 3],
     [4, 5, 6]]
```

**🎯 À retenir :**
- Utilisée pour représenter des **transformations**, des **images** (pixels), ou des **réseaux** de données
- Visualisation : comme une **feuille Excel** avec des chiffres

---

### ✅ 3. Transposée
**Définition :** On échange lignes et colonnes.

**Exemple :**
```python
Matrice originale:    Transposée:
[[1, 2],             [[1, 3],
 [3, 4]]     →        [2, 4]]
```

**🎯 À retenir :**
- C'est comme **faire pivoter la grille**
- Souvent utilisée pour rendre les tailles de matrices compatibles lors des multiplications

---

### ✅ 4. Shape (Forme)
**Définition :** La forme d'une matrice est `(nb_lignes, nb_colonnes)`.

**Exemple :**
```python
M.shape = (2, 3)  # 2 lignes, 3 colonnes
```

**🎯 À retenir :**
- Très utile pour **déboguer**
- Permet de savoir si deux matrices peuvent être multipliées
- En Python : `M.shape` donne cette information

---

### ✅ 5. Axe (Axis)
**Définition :** Direction du calcul dans une matrice.

```python
axis=0  # vertical (par colonne)
axis=1  # horizontal (par ligne)
```

**🎯 À retenir :**
- Détermine le **sens du calcul**
- Exemple : `np.sum(M, axis=0)` calcule la somme **colonne par colonne**

---

## 🔷 Opérations sur les données

### ✅ 6. Slice (Découpage)
**Définition :** Extraire une partie d'un tableau.

**Exemples :**
```python
v[1:3]     # éléments d'indice 1 et 2
M[:, 0]    # toutes les lignes, colonne 0
M[1, :]    # ligne 1, toutes les colonnes
v[::2]     # un élément sur deux
M[0:2, 1]  # lignes 0 et 1, colonne 1
```

**🎯 À retenir :**
- Très pratique pour analyser ou modifier une portion d'un tableau
- Slicing = rapide et sans copie mémoire !
- On peut chaîner les slices pour des opérations avancées

---

### ✅ 7. Opérations élément par élément
**Définition :** Opérations effectuées sur chaque case individuellement.

**Exemples :**
```python
a = [1, 2, 3]
b = [4, 5, 6]
a + b → [5, 7, 9]   # addition
a * b → [4, 10, 18] # multiplication
```

**🎯 À retenir :**
- Aussi appelées **opérations vectorisées**
- Beaucoup plus rapide que des boucles `for`
- Utilisé partout en IA, traitement d'images, etc.

---

### ✅ 8. Concaténation
**Définition :** Assembler plusieurs vecteurs ou matrices.

**Exemples :**
```python
np.concatenate((a, b))   # coller à la suite
np.vstack((a, b))        # empiler verticalement
np.hstack((a, b))        # coller horizontalement
```

**🎯 À retenir :**
- Important pour créer des batches de données
- Utile pour fusionner des résultats
- ⚠️ Attention aux shapes compatibles

---

## 🔷 NumPy et calculs avancés

### ✅ 9. Produit scalaire (Dot Product)
**Définition :** Multiplie chaque élément avec l'autre + fait la somme.

**Exemple :**
```python
np.dot([1,2,3], [4,5,6]) = 1*4 + 2*5 + 3*6 = 32
```

**🎯 À retenir :**
- Résultat = **un seul nombre**
- Utilisé pour mesurer la similarité entre deux vecteurs
- Applications : moteurs de recherche, IA

---

### ✅ 10. Multiplication de matrices
**Définition :** Multiplie lignes de la première avec colonnes de la seconde.

**Syntaxe :**
```python
A @ B        # notation moderne
np.dot(A, B) # notation classique
```

**🎯 À retenir :**
- Ce n'est **pas** une opération élément par élément
- Très utilisée dans les réseaux de neurones, les graphes, la 3D
- ⚠️ `A @ B ≠ B @ A` (non commutative)

---

### ✅ 11. NumPy
**Définition :** Bibliothèque Python pour le calcul scientifique.

**Fonctionnalités :**
- Tableaux (vecteurs, matrices)
- Calcul scientifique
- Performance optimisée

**🎯 À retenir :**
- Utilisé dans presque tous les domaines scientifiques en Python
- Très bien intégré avec Pandas, Scikit-learn, TensorFlow
- Base indispensable pour la data science

---

### ✅ 12. Parallélisation
**Définition :** Diviser les calculs sur plusieurs cœurs pour accélérer.

**Fonctionnement :**
- NumPy utilise des librairies comme BLAS/LAPACK

**🎯 À retenir :**
- Permet d'exécuter des milliers de calculs simultanément
- Rend l'IA et la data science possibles à grande échelle

---

### ✅ 13. Broadcasting
**Définition :** Permet d'opérer sur des tableaux de formes différentes.

**Exemple :**
```python
a = [1, 2, 3]
b = [[10], [20]]
a + b = [[11, 12, 13],
         [21, 22, 23]]
```

**🎯 À retenir :**
- Très puissant pour simplifier le code
- ⚠️ Attention aux erreurs silencieuses si les dimensions sont mal comprises

---

### ✅ 14. Magnitude d'un vecteur
**Définition :** La magnitude (ou norme) d'un vecteur, c'est sa longueur dans l'espace.

**Exemple :**
```python
v = [3, 4] → magnitude = √(3² + 4²) = 5
```

**🎯 À retenir :**
- Visualisation : comme la taille d'une flèche
- Utilisé pour normaliser les vecteurs : `v / ||v||`
- En IA : très utile pour les distances, similarités

---

## 🔷 Tableau récapitulatif

| **Terme** | **Sens simplifié** |
|-----------|-------------------|
| Vecteur | Rangée de nombres |
| Matrice | Grille de nombres |
| Transposée | Pivot de la grille |
| Shape | Taille de la grille |
| Axe | Sens du calcul |
| Slice | Découpage |
| Dot product | Multiplication + addition |
| Broadcasting | Étirement intelligent des tailles |
| NumPy | Boîte à outils des tableaux |
| Magnitude | Longueur d'un vecteur |

---

## 🔷 Défis pratiques

### 🤔 Questions de compréhension
1. **Que se passe-t-il si les formes de matrices ne correspondent pas ?**
2. **Pourquoi A @ B ≠ B @ A ?**
3. **Peux-tu dessiner une matrice 2×3 et sa transposée ?**
4. **Peux-tu écrire un perceptron en NumPy uniquement ?**

### 💡 Exercices pratiques
- Créer des exemples concrets pour chaque concept
- Implémenter les opérations de base sans NumPy, puis avec NumPy
- Analyser les performances entre boucles Python et opérations vectorisées

---

## 📌 Points clés à retenir

> **Performance** : NumPy est optimisé pour les calculs vectoriels  
> **Flexibilité** : Broadcasting permet des opérations sur différentes formes  
> **Applications** : Base de l'IA, data science, calcul scientifique  
> **Debugging** : Toujours vérifier les shapes avant les opérations  

---

*Fiche créée pour le Peer Learning Day - Spécialisation C#25*
