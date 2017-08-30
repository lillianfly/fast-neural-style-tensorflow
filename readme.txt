测试：sudo python eval.py --model_file models/mosaic.ckpt-done  --image_file img/test.jpg

Train a Model:

To train a model from scratch, you should first download VGG16 model from Tensorflow Slim. Extract the file vgg_16.ckpt. Then copy it to the folder pretrained/ :

cd <this repo>
mkdir pretrained
cp <your path to vgg_16.ckpt>  pretrained/
Then download the COCO dataset. Please unzip it, and you will have a folder named "train2014" with many raw images in it. Then create a symbol link to it:

cd <this repo>
ln -s <your path to the folder "train2014"> train2014
Train the model of "wave":

python train.py -c conf/wave.yml
(Optional) Use tensorboard:

tensorboard --logdir models/wave/
Checkpoints will be written to "models/wave/".

View the configuration file for details.
