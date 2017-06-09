WWDC 2017

Table of Contents
=================

  * [Using Metal 2 for Compute \- Thursday](#using-metal-2-for-compute---thursday)
    * [MPS (Metal Performance Shader)](#mps-metal-performance-shader)
      * [Image Processing](#image-processing)
      * [Linear Algebra](#linear-algebra)
    * [Accelerating ML Using MPS](#accelerating-ml-using-mps)
      * [Training &amp; Inference](#training--inference)
    * [Convolutional Neural Networks](#convolutional-neural-networks)
    * [Neural Network Graph API](#neural-network-graph-api)
    * [Summary](#summary)

# Using Metal 2 for Compute - Thursday
Session video and resources: https://developer.apple.com/videos/play/wwdc2017/608/

## MPS (Metal Performance Shader)
  - MPS is now supported on macOS as well
### Image Processing
### Linear Algebra

## Accelerating ML Using MPS
### Training & Inference
  - Training to classify images -> Inference via CNN (Convolutional Neural Network)
    - First part is one time, highly time consuming training phase
    - Second part could be accelerated by using MPS

## Convolutional Neural Networks

## Neural Network Graph API
  - Describe neural networks using graph API
  - Initialize once, reuse
  - Execute graph on GPU with single call

## Summary
  - GPU accelerated primitives
    - Extended support for image processing
    - Addes support for linear algebra
  - Optimized for iOS and macOS
  - New neural network graph API
