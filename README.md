# GLaDOS Text-to-speech (TTS) Voice Generator
Neural network based TTS Engine.

If you want to just play around with the TTS, this works as stand-alone.
```console
python3 glados-tts/glados.py
```

the TTS Engine can also be used remotely on a machine more powerful then the Pi to process in house TTS: (executed from glados-tts directory
```console
python3 engine-remote.py
```

Default port is 8124
Be sure to update settings.env variable in your main Glados-voice-assistant directory:
```
TTS_ENGINE_API			= http://192.168.1.3:8124/synthesize/
```


## Description
The initial, regular Tacotron model was trained first on LJSpeech, and then on a heavily modified version of the Ellen McClain dataset (all non-Portal 2 voice lines removed, punctuation added).

* The Forward Tacotron model was only trained on about 600 voice lines.
* The HiFiGAN model was generated through transfer learning from the sample.
* All models have been optimized and quantized.



## Installation Instruction
If you want to install the TTS Engine on your machine, please follow the steps
below.

1. Install [`python 3.7.9`](https://www.python.org/downloads/release/python-379/).
   If you have to deal with multiple versions of python then you may find [`pyenv-win`](https://pypi.org/project/pyenv-win/) extremely helpful
2. Install the [`espeak`](https://github.com/espeak-ng/espeak-ng) synthesizer
   according to the [installation
   instructions](https://github.com/espeak-ng/espeak-ng/blob/master/docs/guide.md)
   for your operating system.
3. Install the required Python packages, e.g., by running `pip install -r
   requirements.txt`
4. Set the required environment variables by running
```console
setx PHONEMIZER_ESPEAK_LIBRARY 'c:/Program Files/eSpeak NG/libespeak-ng.dll'
setx PHONEMIZER_ESPEAK_PATH 'c:/Program Files/eSpeak NG/espeak-ng.exe'
```
   
## TTS Voice Wizard Instructions
- Follow the above installation instructions
- To use glados TTS for TTS Voice Wizard run this (it will need to be running in the background for Glados TTS to work in TTS Voice Wizard)
- open terminal or command prompt
- "cd" into the correct folder then type
```console
python3 engine-TTSVoiceWizard.py
```
or if that doesn't work try
```console
python engine-TTSVoiceWizard.py
```
