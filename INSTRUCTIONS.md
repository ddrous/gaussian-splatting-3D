
# Running 3D Gaussian Splatting on DaffyDuck


Create a suitable environment
```bash
conda env create --file environment.yml
```

Download a dataset
```bash
wget https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/datasets/input/tandt_db.zip
```

Train and save a model for just a few iterations (to minimize memory usage)
```bash
python train.py --iterations=100 --source_path="datasets/tandt/truck/" --model_path="output/cheap_model" --eval
```

Render the trained gaussian model (it also produces images at various training/testing angles)
```bash
python render.py --model_path="output/cheap_model/"
```

Evaluate (for some reason it stills requires VGG16)
```bash
python metrics.py --model_path="output/cheap_model/"
```
