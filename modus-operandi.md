# générer un .exe avec pipenv et pyinstaller

## créer un venv avec pipenv

### installer pipenv
```
pip install -U pip
pip install -U pipenv
```

### créer le venv
* `pipenv install`: 
  * création du venv dans `~/.virtualenvs`
  * création des fichiers **Pipfile** et **Pipfile.lock**

### ajouter des dépendances
* `pipenv install requests`: installation dans le venv section "prod"
* `pipenv install --dev pytest`: installation dans le venv section "dev"

### exporter les dépendances
* `pipenv requirements > requirements.txt`: dépendances de prod
* `pipenv requirements --dev-only > req-dev.txt`: dépendances de dev

### installer les dépendances
* `pipenv install -r requirements.txt`

### déinstaller les dépendances
* `pipenv uninstall <package>`
* `pipenv uninstall --all-dev`: rtirer les dépendances dev

### créer l'exe en un fichier avec les deps
* `pipenv run <cmd>`: exécuter dans le venv
* `pipenv run pyinstaller --paths "$(pipenv --venv)\Lib\site-packages" --onefile app.py`: l'appli est dans dist