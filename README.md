🗣️ Speech to Text in Python 📜
==============================

Goals in this project:

1. Explore some Python's tools used for audio manipulation and transcription from speech to text.

2. Transcript audio files from telephonic calls and apply on it sentiment and topic analysis.

During tools exploration phase audio files under different conditions are used. Such as:

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

* `Dutch and English datasets`: [`Common Voice`](https://voice.mozilla.org/en/datasets) is a initiative from Mozilla that offers open source, 
multi-language dataset of voices that anyone can use to train speech-enabled applications. At this moment you can have access to 
18 different languages. You download not only audio files but also other .tsv files with information about those audio files. Really 
great resource!

* `LibriSpeech`: [`LibriSpeech`](http://www.openslr.org/12/) is a carefully segmented and aligned corpus of approximately 1000 hours of 16kHz 
read English speech, derived from 
read audiobooks. I downloaded only `dev-clean.tar.gz`.

* `Multiuser audio files`: There are two datasets:

    - [`Call Friend`](https://ca.talkbank.org/access/CallFriend/)
    - [`Call Home`](https://ca.talkbank.org/access/CallHome/)
    
Both have some different languages (unfortunatelly not Dutch) and audios are both in `wav` and `mp3`. In addition, you can have the 
transcriptions. 

# Notebooks

**[01-Speech Transcription using Speech Recognition and PyDub](https://github.com/dpbac/speech_to_text_with_python/blob/master/notebooks/01-Speech%20Transcription%20using%20Speech%20Recognition%20and%20PyDub.ipynb)**:
Use `PyDub` to access audio file information and modify audio files before performing transcriptions with `SpeechRecognition` and `Speech Google API`.

**[](https://github.com/dpbac/speech_to_text_with_python/blob/master/notebooks/02-Phonecalls_analysis.ipynb)**


# Install/Technical requirements

* You'll need Twitter API credentials to run this project. In [01-collecting_and_saving_tweets.ipynb](https://github.com/dpbac/twitter_analysis_online_grocery_NL/blob/master/notebooks/01-collecting_and_saving_tweets.ipynb) replace `private_twitter_credentials.py` by `twitter_credentials.py`. `twitter_credentials.py` must contain your [Twitter 
credentials](https://developer.twitter.com/en/docs/basics/authentication/oauth-1-0a/obtaining-user-access-tokens).

* conda version: 4.8.3
* Install requirements using `pip install -r requirements.txt`.
  * Make sure you use Python 3 (I used 3.6.7).
  * You may want to use a virtual environment for this.


--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>
