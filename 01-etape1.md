---
# Étape 1 : Installer Anaconda
---

- https://www.anaconda.com/download


---
# Étape 2 - Exécution des commandes suivantes:
---

- Avant d'exécuter les commandes dans les sections Option 1 ou Option 2, ouvrez **Anaconda** et accédez à l'onglet **Environnements**.  
- Créez un nouvel environnement en sélectionnant **Python 3.9** ou une autre version, ou choisissez un environnement existant.  
- Cliquez sur la **flèche verte** à l'extrémité droite de l'onglet **Environnements** et ouvrez le terminal.  
- **Tapez** la commande `deactivate`.  
- Ces étapes sont nécessaires pour exécuter les commandes ci-dessous. Si vous ouvrez directement l'invite de commande (**cmd**), cela ne fonctionnera pas.
  
## Option 1  - pycaret==2.0 est compatible avec python=3.9

```
conda create --name myenv1 python=3.9
conda activate myenv1 
pip install pycaret==2.0
pip freeze > requirements.txt
pip install -r requirements.txt
deactivate
```

## Option 2  - pycaret==3.x est compatible avec python=3.12

```
conda create --name myenv2 python=3.12
conda activate myenv2
pip install pycaret
pip install pycaret==3.3.2 
pip freeze > requirements.txt
pip install -r requirements.txt
deactivate
```


---
# Étape 3 - Dans Power BI 
---


1. Allez dans :  
   *Fichier* > *Options et paramètres* > *Options*
2. Sélectionnez *Scripts Python*
3. Choisissez le chemin Python de votre environnement `myenv`  
   (par exemple, `C:\Users\VotreNom\anaconda3\envs\myenv\python.exe`)



---
# Étape 4 - Dans Power BI 
---


## Références AutoML

- [Google Drive](https://drive.google.com/drive/folders/1zzZNeNzjWeLx8j_erX6yoPDcoIUuQZiR?usp=sharing)  
- [Vidéo YouTube](https://www.youtube.com/watch?v=kohLQfsVE5Y&ab_channel=TheBIHub)  

### Instructions

1) Rendez-vous sur **Power BI en ligne** et non sur l'application Desktop de Power BI : [Power BI Service](https://app.powerbi.com/home?experience=power-bi).  
2) Cliquez sur votre profil.  
3) Démarrez l'essai gratuit si nécessaire.  
4) Cliquez sur l'onglet **Espaces de travail** (situé à droite).  
5) Créez un nouvel espace de travail (**+ Nouvel espace de travail**).  
6) Sous l'espace de travail, cliquez sur **Nouvel élément**, puis cherchez **Gen1** dans la barre de recherche.  
7) Choisissez **Créer un dataflow Gen1** et non **Gen2**, même si celui-ci est proposé.  

![image](https://github.com/user-attachments/assets/3cb2affe-ad2a-4237-9778-a85d7a7d0b0f)  

![image](https://github.com/user-attachments/assets/3a45b788-5972-42a2-9b2b-ec1560fc6677)  

---
# Annexe 1 - Vérifier la version via Python
---

Pour vérifier la version de **PyCaret** une fois installé, vous pouvez utiliser l'une des commandes suivantes :

### 1️⃣ Vérifier la version via Python
Ouvrez un terminal ou un Jupyter Notebook et tapez :

```python
import pycaret
print(pycaret.__version__)
```

### 2️⃣ Vérifier la version via `pip`
Dans le terminal (ou l'invite de commande), tapez :

```bash
pip show pycaret
```

Cela affichera des informations sur le package, y compris sa version.

### 3️⃣ Vérifier la version via `conda`
Si vous avez installé **PyCaret** via `conda`, utilisez :

```bash
conda list pycaret
```

Cela affichera la version installée ainsi que d'autres détails.

---

**💡 Conseil :** Assurez-vous d'avoir activé l'environnement où **PyCaret** est installé avant d'exécuter ces commandes :

```bash
conda activate myenv
```






---
## Annexe 2 -Liste de commandes Anaconda 
---

###  **Lister les environnements Conda disponibles**  
```bash
conda env list
```
ou en version raccourcie :  
```bash
conda info --envs
```
**Affiche la liste complète des environnements Conda avec leurs chemins.**

### 🗑 **Supprimer un environnement Conda**  
```bash
conda remove --name nom_de_ton_env --all
```
**Remplace `nom_de_ton_env` par le nom exact de l’environnement à supprimer.**  

Exemple : Pour supprimer un environnement nommé `test_env` :  
```bash
conda remove --name test_env --all
```

---

### **Vérifier que l’environnement a bien été supprimé**  
```bash
conda env list
```
**Permet de s'assurer que l'environnement n'est plus listé.**


💡 **Astuce** : Si l’environnement est toujours listé après suppression, essaie de redémarrer ton terminal. 🚀



---
## Annexe 3
---

```
conda create --name myenv python=3.12
conda activate myenv
# Sur Linux : source activate myenv
# Passer à **PyCaret 3.x** *(si ton projet le permet)*  
pip install pycaret
#_(Cela installera la dernière version stable disponible)_
# Passer à **PyCaret 3.x** *(si ton projet le permet)*  
# En cas d'erreur : pip install --upgrade pip
```






```
conda create --name myenv python=3.12
conda activate myenv
# Sur Linux : source activate myenv
# Passer à **PyCaret 3.x** *(si ton projet le permet)*  
pip install pycaret
#_(Cela installera la dernière version stable disponible)_
# Passer à **PyCaret 3.x** *(si ton projet le permet)*  
# En cas d'erreur : pip install --upgrade pip
```

```
conda create --name myenv python=3.12
conda activate myenv 
pip install pycaret==3.3.2 (pip install pycaret==3.x)
```





### 🔄 **Option 2 : Trouver une version de PyCaret compatible avec `sklearn`**
Si tu veux absolument rester sur **PyCaret 2.0**, essaie une version spécifique de `scikit-learn` qui était compatible à l’époque :

```bash
pip install pycaret==2.0
```

---

### 🛠 **Résumé des options possibles :**
- **Option 1** : Installer PyCaret 3.X (pycaret dernière version pip install pycaret)
- **Option 2** : Installer une version spécifique de `scikit-learn` et de `python` compatible avec PyCaret 2.0  









