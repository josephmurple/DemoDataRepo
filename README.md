# DemoDataRepo


The command to make dataset

    $ git init
    $ dvc init
    $ git status
    $ git commit -m "Init Repo"

    # Remote Data path: D:\dvc-storage-remote
    $ dvc remote add -d dvc-remote /d/dvc-storage-remote
      
    # check config 
    $ cat .dvc/config
    
    $ git commit .dvc/config -m "configure remote storage"
    
    # make dataset folder, copy data(wine-quality.csv) into it.
    $ mkdir data
    $ dvc add data/wine-quality.csv

    $ cat data/wine-quality.csv.dvc
    $ cat data/.gitignore
      
    $ git add 'data\wine-quality.csv.dvc' 'data\.gitignore'
    $ git commit -m "Data: track"
    
    # Attach tag V1 for easy control
    $ git tag -a 'v1' -m 'raw data'
      
    # push data to remote 
    $ dvc push
      
    # Chage data to make V2, remove 1000 lines
    $ sed -i '2,1001d' data/wine-quality.csv
    
    $ ll -h data/wine-quality.csv
    
    $ dvc add data/wine-quality.csv
    $ git add 'data\wine-quality.csv.dvc'
    
    $ git commit -m 'data: remove 1000 lines'
    
    # Attach tag V1 for easy control
    $ git tag -a 'v2' -m 'remove 1000 lines'
    
    $ dvc push

