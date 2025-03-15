# Code complet à tester  via Colab

```python
# Installation de PyCaret
!pip install pycaret[full]

# Importation des bibliothèques nécessaires
import pandas as pd
from pycaret.classification import *

# Chargement du dataset bancaire
url = 'https://raw.githubusercontent.com/pycaret/pycaret/master/datasets/bank.csv'
dataset = pd.read_csv(url) 

# Affichage des premières lignes du dataset
print("Aperçu des données :")
print(dataset.head())

# Configuration de l'environnement PyCaret
clf1 = setup(dataset, target='deposit', train_size=0.6, silent=True, session_id=123)

# Entraînement d'un modèle XGBoost
xgboost = create_model('xgboost', verbose=False)

# Comparaison des modèles et sélection du meilleur
best_model = compare_models(verbose=False)

# Finalisation du meilleur modèle (réentraînement sur 100% des données)
best = finalize_model(best_model)

# Affichage des informations du meilleur modèle
print("\nMeilleur modèle sélectionné :")
print(best)

# Récupération du dataset après transformation par PyCaret
dataset_transformed = pull()

# Affichage des premières lignes du dataset transformé
print("\nDataset transformé :")
print(dataset_transformed.head())

# Sauvegarde du modèle XGBoost (décommentez pour sauvegarder)
# save_model(xgboost, 'xgboost_bank_model')
```

### **💡 Explication des modifications et ajouts :**
1. **Ajout de `silent=True` et `session_id=123`** dans `setup()` :
   - `silent=True` empêche PyCaret de demander des confirmations à l’utilisateur.
   - `session_id=123` garantit la reproductibilité des résultats.
  
2. **Ajout de `print()` pour afficher des informations utiles** :
   - `dataset.head()` pour visualiser les premières lignes avant transformation.
   - `print(best)` pour voir les détails du modèle sélectionné.
   - `dataset_transformed.head()` pour observer comment PyCaret transforme les données.

3. **Utilisation de `pull()` pour récupérer le dataset transformé** après l'encodage et le prétraitement appliqués par PyCaret.

4. **Ajout d’un commentaire pour la sauvegarde du modèle** :
   - `save_model(xgboost, 'xgboost_bank_model')` permet d’enregistrer le modèle pour une utilisation future.

 **Ce code effectue un pipeline complet en AutoML** :
- Charge un dataset 
- Prétraite les données 
- Compare plusieurs modèles 
- Sélectionne et entraîne le meilleur 
- Affiche les résultats   
- Transforme les données 
- Sauvegarde le modèle (optionnel) 

**Idéal pour automatiser la sélection et le déploiement de modèles ML sur des données structurées !** 
