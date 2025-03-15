# Exemple d'analyse exploratoire des données (EDA) sur le fichier CSV de la banque. 

- Cette analyse inclut :

1. **Chargement des données**  
2. **Affichage des premières lignes**  
3. **Informations générales sur le dataset**  
4. **Statistiques descriptives**  
5. **Détection des valeurs manquantes**  
6. **Distribution des variables numériques**  
7. **Analyse des variables catégorielles**  
8. **Visualisation des corrélations**  

### **Analyse exploratoire des données (EDA) en Python**
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Charger les données
df = pd.read_csv("bank.csv")  # Assurez-vous que le fichier est dans le même dossier que ce script

# 1. Afficher les premières lignes
print("Aperçu des premières lignes du dataset :")
print(df.head())

# 2. Afficher les colonnes du dataset
print("\nColonnes du dataset :")
print(df.columns)

# 3. Afficher les informations générales
print("\nInformations générales :")
print(df.info())

# 4. Statistiques descriptives
print("\nStatistiques descriptives :")
print(df.describe())

# 5. Vérification des valeurs manquantes
print("\nValeurs manquantes par colonne :")
print(df.isnull().sum())

# 6. Affichage de la distribution des variables numériques
numeric_cols = df.select_dtypes(include=['number']).columns
df[numeric_cols].hist(figsize=(12, 8), bins=20, edgecolor="black")
plt.suptitle("Distribution des variables numériques")
plt.show()

# 7. Affichage de la distribution des variables catégorielles
categorical_cols = df.select_dtypes(include=['object']).columns
fig, axes = plt.subplots(len(categorical_cols), 1, figsize=(10, len(categorical_cols) * 3))
for i, col in enumerate(categorical_cols):
    sns.countplot(y=df[col], ax=axes[i], order=df[col].value_counts().index)
    axes[i].set_title(f"Distribution de {col}")
plt.tight_layout()
plt.show()

# 8. Matrice de corrélation
plt.figure(figsize=(10, 6))
sns.heatmap(df.corr(), annot=True, cmap="coolwarm", fmt=".2f")
plt.title("Matrice de corrélation")
plt.show()
```

---

### **Explication**
1. **Chargement des données** → `pd.read_csv("bank.csv")`
2. **Aperçu des premières lignes** → `df.head()`
3. **Colonnes disponibles** → `df.columns`
4. **Informations générales (types, valeurs non nulles)** → `df.info()`
5. **Statistiques descriptives** → `df.describe()`
6. **Valeurs manquantes** → `df.isnull().sum()`
7. **Visualisation des distributions numériques** → `df[numeric_cols].hist()`
8. **Distribution des variables catégorielles** → `sns.countplot()`
9. **Matrice de corrélation** → `sns.heatmap(df.corr())`
