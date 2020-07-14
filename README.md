Speech to text 
==============================

We have two goals in this project:

1. Explore some Python's tools used for audio manipulation and transcription from speech to text.

2. Transcript audio files from telephonic calls and apply on it sentiment and topic analysis.

During the tools exploration phase audio files in different conditions are used. Such as:

* Different languages of speakers (english and dutch)

* Multiple speaker with multiple channels

* Presence of noise

The tools explored in this project are:

* [`SpeechRecognition`](https://pypi.org/project/SpeechRecognition/): This Python library provides an easy way to interact with many 
speech-to-text APIs.

* [`Google Speech API`](https://cloud.google.com/speech-to-text): From the Speech APIs available to use within SpeechRecognition 
will be using a free version of `Google Speech API`. In addition, the free version does not support `speaker diarization` which 
is the process of splitting more than one speaker from a single audio. It is also not possible to detect punctuation. It supports 
different [languages](https://cloud.google.com/speech-to-text/docs/languages). Currently the following limits are applied:

![](https://github.com/dpbac/speech_to_text_with_python/blob/master/images/google_speech_api_limits.JPG)

* [`PyDub`](https://github.com/jiaaro/pydub): Allows different types of audio manipulation

# Datasets

When searching for datasets I had two goals in mind:

* Having a dataset of Dutch Speakers: I live in The Netherlands and I'll be working with audio of Dutch Speakers

* Having a dataset of phone calls with 2 channels: I'll be also probably working in a project that involves calls. Having a two channel 
allows to separated the audio of the two speakers using `PyDub`

Luckily I succeed in obtaining both goals:

* `Dutch dataset`: [`Common Voice`](https://voice.mozilla.org/en/datasets) is a initiative from Mozilla that offers open source, 
multi-language dataset of voices that anyone can use to train speech-enabled applications. At this moment you can have access to 
18 different languages. You download not only audio files but also other .tsv files with information about those audio files. Really 
great resource!

* `Multiuser audio files`: There are two datasets:

    - [`Call Friend`](https://ca.talkbank.org/access/CallFriend/)
    - [`Call Home`](https://ca.talkbank.org/access/CallHome/)
    
Both have some different languages (unfortunatelly not Dutch) and audios are both in `wav` and `mp3`. In addition, you can have the 
transcriptions. 

Project Organization
------------

    ├── LICENSE
    ├── Makefile           <- Makefile with commands like `make data` or `make train`
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── docs               <- A default Sphinx project; see sphinx-doc.org for details
    │
    ├── models             <- Trained and serialized models, model predictions, or model summaries
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── references         <- Data dictionaries, manuals, and all other explanatory materials.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting
    │
    ├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
    │                         generated with `pip freeze > requirements.txt`
    │
    ├── setup.py           <- makes project pip installable (pip install -e .) so src can be imported
    ├── src                <- Source code for use in this project.
    │   ├── __init__.py    <- Makes src a Python module
    │   │
    │   ├── data           <- Scripts to download or generate data
    │   │   └── make_dataset.py
    │   │
    │   ├── features       <- Scripts to turn raw data into features for modeling
    │   │   └── build_features.py
    │   │
    │   ├── models         <- Scripts to train models and then use trained models to make
    │   │   │                 predictions
    │   │   ├── predict_model.py
    │   │   └── train_model.py
    │   │
    │   └── visualization  <- Scripts to create exploratory and results oriented visualizations
    │       └── visualize.py
    │
    └── tox.ini            <- tox file with settings for running tox; see tox.readthedocs.io


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
