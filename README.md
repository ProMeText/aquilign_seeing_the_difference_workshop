# AQUILIGN -- Mutilingual aligner and collator -- démonstration atelier biblissima+


## Utilisation
Les notebooks présents sur ce dépôt ne sont pas utilisables avec binder en raison des ressources en mémoire importantes requises par les modèles de langue. 
Nous vous recommandons de les lancer en local à l'aide de jupyter lab par exemple.

## Prérequis

- Au moins 8 Go de mémoire
- Une trentaine de Go d'espace disponible pour l'entraînement complet
  des modèles de segmentation (étape pouvant être passée)

### Clônage du dépôt et création d'un environnement virtuel

Un environnement virtuel permet d'isoler l'installation des librairies d'un projet pour éviter les conflits de version. Une fois placés dans le répertoire de votre choix:

```
git clone https://github.com/ProMeText/atelier_biblissima_aquilign
cd atelier_biblissima_aquilign
```

Il suffit ensuite d'installer venv si ce n'est déjà fait `pip install --user virtualenv`. Le code a été vérifié sur la version 3.10 de python. 

```
python3.10 -m venv atelier_biblissima_env
source atelier_biblissima_env/bin/activate
pip3 install -r requirements.txt
```

### Installation de ipykernel et mise en relation de l'environnement virtuel


Nous utilisons ici l'excellent manuel de Nikolai Janakiev: [https://janakiev.com/blog/jupyter-virtual-envs/](https://janakiev.com/blog/jupyter-virtual-envs/).

```
pip3 install ipykernel 
python -m ipykernel install --name=atelier_biblissima_env
```

Le terminal devrait retourner: `Installed kernelspec myenv in /home/user/.local/share/jupyter/kernels/myenv`. Vous pouvez afficher le fichier `kernel.json` présent dans le répertoire indiqué par l'outil pour vérifier que le kernel pourra bien utiliser l'environnement virtuel créé: 

```json
{
 "argv": [
  "le_chemin_vers_le_python_de_l_environnement_virtuel",
  "-m",
  "ipykernel_launcher",
  "-f",
  "{connection_file}"
 ],
 "display_name": "venv",
 "language": "python"
}
```

C'est bon ! Il suffit maintenant d'ouvrir jupyterlab: `jupyter lab` et les notebooks dans l'ordre de la séance.

