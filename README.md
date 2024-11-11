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

---


This repo contains a set of scripts to align (and soon collate) a multilingual medieval corpus. Its designers are Matthias Gille Levenson, Lucence Ing and Jean-Baptiste Camps.  

It is based on a fork of the automatic multilingual sentence aligner Bertalign.

The scripts relies on a prior phase of text segmentation at syntagm level using regular expressions or bert-based segmentation to match grammatical syntagms and produce a more precise alignment.

## Use

`python3 main.py -o lancelot -i data/extraitsLancelot/ii-48/ -mw data/extraitsLancelot/ii-48/fr/micha-ii-48.txt -d 
cuda:0 -t bert-based` to perform alignment with our bert-based segmenter, choosing Micha edition as base witness,
on the GPU. The results will be saved in `result_dir/lancelot`

`python3 main.py --help` to print help.

Files must be sorted by language, using the ISO_639-1 language code as parent directory name (`es`, `fr`, `it`, `en`, etc).
## Citation

Lei Liu & Min Zhu. 2022. Bertalign: Improved word embedding-based sentence alignment for Chinese–English parallel corpora of literary texts, *Digital Scholarship in the Humanities*. [https://doi.org/10.1093/llc/fqac089](https://doi.org/10.1093/llc/fqac089).


## Licence

This fork is released under the [GNU General Public License v3.0](./LICENCE)

