WWDC 2017

# Natural Language Processing (NLP) * Wednesday
  - Typed, recognized handwriting, transcribed speech
## NLP APIs
  - Natural language text -> Language identification
  - Natural language text -> Tokenization -> Tokenize text
  - Natural language text -> Part of speech -> Assign parts of speech
  - Natural language text -> Lemmatization -> Lemmatize text
  - Natural language text -> Named entity recognition

## `NSLinguisticTagger`
  - Used for segmenting and tagging text
  - Omitting whitespaces and punctuation is also possible
  - Pass in schemas for options like lemmatization, language identification etc.
### Tagging Units
  - `public enum NSLinguisticTaggerUnit`
    - word
    - sentence
    - paragraph
    - document
  - `dominantLanguage`
  - Improved performance
  - Higher accuracy
  - Additional language support

### Use Case
  - A simple photo app with tagged descriptions
    - A query for an example word like `hike` will return related results via NLP. Rather than just searching for the exact word `hike`
    - Recognizes dominant language and analyses through lemmatization
  - A social media app merging all major social media providers
    - Organize feeds by people, organization and location using NLP

## Why should you use the NLP API's
  - Homogeneous text processing
    - Consistent UX and results across all platforms and devices
  - Privacy
    - On-device machine learning
  - Performance
    - Multi-threaded
    - 50K tokens/sec in a single thread, 80K tokens/sec in a multi-thread
  - Language support
    - 29 scripts, 52 languages for language identification
    - Tokenization for all iOS/macOS languages
