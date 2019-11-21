https://github.com/NVlabs/noise2noise

## Step 1  convert dataset to tfrecords
python3 dataset_tool_tf.py --input-dir datasets/BSDS300/images/train --out=datasets/bsd300.tfrecords

## Step2 download kodak validation
python3 download_kodak.py --output-dir=datasets/kodak

## Step 3 train
python3 config.py --desc='-test' train --train-tfrecords=datasets/bsd300.tfrecords --long-train=true --noise=gaussian