# TensorFlow-ImageClassifier

this classifier classifies flower from 5 categories.
*Daisy, Dandelion, Roses, Sunflowers and Tulip*

## Prerequisite
1) Docker 

## Steps
1) Run Docker Quick Start Terminal
2) Install TensorFlow using "docker run -it gcr.io/tensorflow/tensorflow:latest-devel"
3) run "git pull https://github.com/googlecodelabs/tensorflow-for-poets-2"
4) cd cd tensorflow-for-poets-2
5) run IMAGE_SIZE=224 ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"
6) run below script to train your model 
    python -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=500 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=tf_files/flower_photos
 
 /* It may take while depending upon your hardware */
 
 7) its time to test our model run this script in docker shell !
      python -m scripts.label_image \
    --graph=tf_files/retrained_graph.pb  \
    --image=tf_files/flower_photos/daisy/21652746_cc379e0eea_m.jpg
    
## Result
![output](https://github.com/NeelkanthDabhi/TensorFlow-ImageClassifier/blob/master/result.png)
## Reference
[Code Labs](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/#0)
