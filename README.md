tequ-node-red-object-detection-tf2-sm
=====================

Detect objects from image using Tensorflow 2 SavedModel.

## Install

Run the following command in your Node-RED user directory - typically `~/.node-red`

        npm install tequ-node-red-object-detection-tf2-sm

## Information

Run prediction on input image using Tensorflow 2 Savedmodel.

Input image must be image buffer in **'msg.payload'**.

Outputs:
- Prediction result
- Metagraph (tf.node.getMetaGraphsFromSavedModel)
- Tensorflow memory status (tf.memory())

Excepts following content in model folder:
- saved_model.pb (Tensorflow 2 saved model)
- variables (folder that might include files for saved model)
- labels.json (array of label strings that model can detect)
- metadata.json (metadata of used model in JSON-format, optional)

Supported image formats:
- JPG, PNG, BMP, GIF

Supports:
- Saved model trained using tequ-tf2-ca-training-pipeline
- TensorFlow 2 Detection Model Zoo models:
    - SSD MobileNet v2 320x320 
    - SSD MobileNet V2 FPNLite 320x320	
    - SSD MobileNet V2 FPNLite 640x640

Others might work too, but have not been tested.

To train a model, please look:

https://github.com/Lapland-UAS-Tequ/tequ-tf2-ca-training-pipeline

Dependencies:
- https://www.npmjs.com/package/@tensorflow/tfjs-node-gpu
- https://flows.nodered.org/node/node-red-contrib-image-info
