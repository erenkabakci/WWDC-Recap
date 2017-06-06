WWDC 2017

# Machine Learning (CoreML) * Tuesday
## Why ?
  - Real time image recognition
  - Text prediction
  - Entity recognition
  - Style transfer
  - Speaker identification and many more...
## Training
  - Learning algorithm -> Model
  - Input -> Model -> Desired Output
  - Challenges
    - Correctness
    - Performance
    - Energy efficiency

## ML Frameworks
  - VisionKit
    - Object tracking
    - Face detection
  - NLP (Natural language processing)
    - Language identification
    - Named entity recognition API
  - Core ML
    - Music tagging (tag parts of the music with data)
    - Image captioning (image -> text)

  - All these are powered with Accelerate and MPS
    - High performance math

## Run on device
    - Privacy
    - Prevent data cost
    - Server cost
    - Always available (24/7)

## Model
  - Function learned from data
  - Observed inputs
  - Predicts outputs
  - Single document
  - Public format
  - Sample models
    - `https://developer.apple.com/machine-learning`
    - Core ML models
    - Ready to use
  - Convert to Core ML using python packages (This is fully open source)

## Development
  - Add your ML Model to your project -> autogeneration to Swift file
