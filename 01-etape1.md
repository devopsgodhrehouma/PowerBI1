---
# Étape 1 : Installer Anaconda
---

- https://www.anaconda.com/download


---
# Étape 2 - Exécution des commandes suivantes:
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
pip install pycaret==3.3.2 (pip install pycaret==3.x)
```





### 🔄 **Option 2 : Trouver une version de PyCaret compatible avec `sklearn`**
Si tu veux absolument rester sur **PyCaret 2.0**, essaie une version spécifique de `scikit-learn` qui était compatible à l’époque :

```bash
pip install scikit-learn==0.23.2
pip install pycaret==2.0
```

---

### 🛠 **Résumé des options possibles :**
- **Option 1** : Installer PyCaret 3.X (pycaret dernière version pip install pycaret)
- **Option 2** : Installer une version spécifique de `scikit-learn` et de `python` compatible avec PyCaret 2.0  








---

**Dans Power BI :**

1. Allez dans :  
   *Fichier* > *Options et paramètres* > *Options*
2. Sélectionnez *Scripts Python*
3. Choisissez le chemin Python de votre environnement `myenv`  
   (par exemple, `C:\Users\VotreNom\anaconda3\envs\myenv\python.exe`)



# Annexe 1 - Vérifier la version via Python


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
