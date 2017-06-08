WWDC 2017

Table of Contents
=================

  * [Core ML in Depth \- Thursday](#core-ml-in-depth---thursday)
    * [Sentimental Analysis](#sentimental-analysis)
    * [Predictive Keyboard](#predictive-keyboard)
      * [Hardware Optimized](#hardware-optimized)
  * [Deploying Core ML Models](#deploying-core-ml-models)
    * [Core ML Tools](#core-ml-tools)
      * [Conversion Workflow](#conversion-workflow)
      * [What's CoreML Tools](#whats-coreml-tools)
    * [Conversion Demo](#conversion-demo)
    * [Summary](#summary)

# Core ML in Depth - Thursday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/710/

## Sentimental Analysis
  - Use case: Sentiment analysis app which gives mood output according to the text input
  - Use NLP (`NSLinguisticTagger`) -> Get Word count and tokenize -> Feed it to the ML model
## Predictive Keyboard
  - Task: Next word prediction
  - Sequence of words -> Model -> Next word choices & state
    - Next word & state is fed into the model recursively
### Hardware Optimized
  - Core ML uses Accelerate on top of CPU and Metal on top of GPU

# Deploying Core ML Models
  - Example models under https://developer.apple.com/machine-learning
## Core ML Tools
  - Fully open sourced
### Conversion Workflow
  - Model Source (e.g Caffe) -> Xcode -> ML Model & Swift ->
  - `pip install coremltools`
### What's CoreML Tools
  - Convert from other formats
  - Build your own converter
  - Compatible & Extensible

## Conversion Demo
Sample python code
```
import coremltools
caffe_model = ('flowers.caffemodel', 'flowers.prototxt')
labels = 'labels.txt'

coreml_model = coremltools.converters.caffe.convert(caffe_model, class_labels=labels, image_input_names='data')
coreml_model

// Output of dictionaries with the results

coreml_model.save('FlowerPredictor.mlmodel')
```
## Summary
  - Easy integration of ML models
  - Rich datatype support
  - Hardware optimized
  - Compatible with popular formats
