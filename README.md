The original README.md is https://github.com/ultralytics/yolov5/blob/master/README.md
# 0. Set up
```
pip install -r requirements.txt
```

# 1. Create crater dataset

First, create a dataset using https://github.com/acse-yl13320/Robbins-to-THEMIS. Then, create a yaml file in data/ folder. You can refer to data/whole.yaml

# 2. Train on the crater dataset
```
python train.py --name run_name --img 593 593 --batch 16 --epochs 50 --data whole.yaml --weights yolov5s.pt
```

# 3. Test performance
```
python3 test.py --name run_name --weights path/to/the/weight/last.pt --data whole.yaml --task test
```
If we want to save a loss ranking list,
```
python3 test.py --name run_name --weights path/to/the/weight/last.pt --data whole.yaml --task test --save-loss
```

# 4. Detect
```
python3 detect.py --name run_name --weights path/to/the/weight/last.pt --source ../Robbins-to-THEMIS/dataset/images --save-txt --hide-labels --save-conf --nosave
```