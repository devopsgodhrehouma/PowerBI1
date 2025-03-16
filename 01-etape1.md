---
# Étape 1 : Installer Anaconda
---

- https://www.anaconda.com/download


---
# Étape 2 - Exécution des commandes suivantes:
---

- Avant d'exécuter ces commandes, il faut ouvrir Anaconda et choisir l'onglet **Environnements**.  
- Créez un nouvel environnement en sélectionnant la version **3.9 de Python** ou n'importe quelle version, sinon sélectionnez un environnement existant.  
- Cliquez sur la **flèche verte** à l'extrémité droite de l'onglet **Environnements** et lancez le terminal.  
- **Écrivez** la commande `deactivate`.

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









