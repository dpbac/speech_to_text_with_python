Speech to Text in Python
==============================

Goals in this project:

1. Explore some Python's tools used for audio manipulation and transcription from speech to text.

2. Transcript audio files from telephonic calls and apply on it sentiment and topic analysis.

During the tools exploration phase audio files in different conditions are used. Such as:

* Different languages of speakers (english and dutch)

* Multiple speaker with multiple channels

* Presence of noise

Project Organization
------------
    │
    ├── README.md          <- The top-level README for developers using this project.
    │
    ├── data
    │   ├── audio_call_friend       <- Audio files downloaded from CallFriend.
    │   ├── audio_call_home         <- Audio files downloaded from CallHome.
    │   ├── audio_common_voices     <- Files downloaded from Common Voices.
    │   │   └── nl                  <- Dutch audio and .tsv files
    │   │       └── raw             <- mp3 files.
    │   ├── audio_openslr           <- Audio file downloaded from LibriSpeech
    │   │    └── dev-clean          <- Dutch audio and .tsv files
    │   │       └── 1272            <- flac files.    
    │   ├── interim        <- Intermediate data that has been transformed.
    │   └── processed      <- The final, canonical data sets for modeling.
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                        `1.0-jqp-initial-data-exploration`.
    │
    ├── images             <- Images used in the project.
    │
    ├──.gitignore          <- Contains entries of files or folders to ignore in a project.
    │
    └── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
	                         generated with `pip freeze > requirements.txt`



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

--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
