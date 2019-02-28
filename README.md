# keras to tf
Convert keras model to tf model for movidius neural compute stick

1. create a sub-directory called "TF_Model"
2. edit the path of model_file(json) and weights_file (HDF5)
3. python keras_to_tf.py

Each file serves a different purpose,

- .checkpoint defines the model checkpoint path which is "tf_model" in our case.
- .meta stores the graph structure,
- .data stores the values of each variable in the graph
- .index identifies the checkpoint.

### Compile TensorFlow model with mvNCCompile
```
mvNCCompile TF_Model/tf_model.meta -in=conv2d_1_input -on=dense_2/Softmax
```
