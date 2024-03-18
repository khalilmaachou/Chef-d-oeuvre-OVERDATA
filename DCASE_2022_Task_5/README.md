

## Comment entraîner le modèle : 

1. Préparer l'environnement : 

Cloner le projet : 
```bash
# clone project
git clone https://github.com/haoheliu/DCASE_2022_Task_5
cd DCASE_2022_Task_5
```
Créer l'environnement conda : 
```
#create conda environment
conda env create -f environment.yml 
conda activate dcase_t5
```

2. Préparer l'entraînement et la validation. Le dataset sera téléchargé grâce au script data_preparation.py.

```bash
python3 data_preparation.py
```

3. Changer le root directory dans ./configs/train.yaml.
Nous pouvons le changer directement sur terminal avec "nano train.yaml". 
```yaml
path:
  root_dir: <your-root-directory> 
# exemple root_dir: /home/utilisateur
```

4. Entrainer le modèle avec la configuration par défaut. Le post-traitement et l'évaluation seront executé automatiquement. 
Avant de lancer le script d'entraînement il faut dupliquer le Development_Set dans le root. 
```bash
# train on CPU
python train.py trainer.gpus=0

# train on GPU
python train.py trainer.gpus=1
```
Pendant l'entraînement il faut suivre les étapes pour créer un compte sur le site wandb.ai (Weight and Biases) afin de pouvoir visualiser les courbes d'entraînement, de validatation etc. et avoir les logs avec les résultats. 


- Les autres options d'entaînement sont dans le fichier train.yaml. 

- Configuration système minimum requise : Mémoire >= 16GB + Un CPU/GPU moderne + Espace libre du disque >= 25G.

## Cite le travail

```bibtex
@techreport{Liu2022a,
    Author = "Liu, Haohe and Liu, Xubo and Mei, Xinhao and Kong, Qiuqiang and Wang, Wenwu and Plumbley, Mark D",
    title = "SURREY SYSTEM FOR DCASE 2022 TASK 5 : FEW-SHOT BIOACOUSTIC EVENT DETECTION WITH SEGMENT-LEVEL METRIC LEARNING",
    institution = "DCASE2022 Challenge Technical Report",
    year = "2022"
}
```


