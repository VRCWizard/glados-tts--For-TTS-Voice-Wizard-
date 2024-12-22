# GLaDOS Text-to-speech (TTS) Voice Generator
Neural network based TTS Engine.

If you want to just play around with the TTS, this works as stand-alone.
```console
python glados-tts/glados.py
```

the TTS Engine can also be used remotely on a machine more powerful then the Pi to process in house TTS: (executed from glados-tts directory
```console
python engine-remote.py
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

1. ~~Install [`python 3.7.9`](https://www.python.org/downloads/release/python-379/)~~ Install [python 3.9.0](https://www.python.org/downloads/release/python-390/).
   If you have to deal with multiple versions of python then you may find [`pyenv-win`](https://pypi.org/project/pyenv-win/) extremely helpful. For Torch/Cuda support refer [here](https://pytorch.org/get-started/locally/#windows-python). Python 3.9.0 is confirmed to work.
   
      - [pyenv quickstart guide](https://github.com/pyenv-win/pyenv-win#quick-start)
      
     ![image](https://user-images.githubusercontent.com/101527472/225459133-9075a959-1d7b-4c77-a017-164fa242acbd.png)
     (pytorch will not install correctly if using 32 bit version)

   
2. Install the [`espeak`](https://github.com/espeak-ng/espeak-ng) synthesizer
   according to the [installation
   instructions](https://github.com/espeak-ng/espeak-ng/blob/master/docs/guide.md)
   for your operating system.
3. Using console (all commands will be typed into console) 
    - open "terminal" or "command prompt"
![image](https://user-images.githubusercontent.com/101527472/215557319-1b7f04e0-eabf-4830-b305-2c31922e037f.png)

    - Change Directory or "cd" into the correct folder with engine-TTSVoiceWizard.py in it, here is an example:

```console
cd C:\Users\<NAME>\Downloads\glados-tts-voice-wizard-main\glados-tts-voice-wizard-main
```
4. type this command into console to see if the correct version of python is installed and working correctly.
```console
python --version
```
- if you get an error that mentions "app execution aliases", simily turn them off for python in the windows settings
    
![image](https://user-images.githubusercontent.com/101527472/225462429-592cfb3b-ee28-4355-9d71-84466aa36a09.png)

5. Install the required Python packages, e.g., by running `pip install -r
   requirements.txt`
    - if it says that pip is not a recognized command use  `python -m pip install -r requirements.txt` instead
    - if it still says pip is not recognized then one of the solutions here is guarrenteed to help (if you ask for help with this issue I will literally tell you a solution verbatium from this page) https://stackoverflow.com/questions/23708898/pip-is-not-recognized-as-an-internal-or-external-command
  
5. Set the required environment variables by running
```console
setx PHONEMIZER_ESPEAK_LIBRARY 'C:\Program Files\eSpeak NG\libespeak-ng.dll'
setx PHONEMIZER_ESPEAK_PATH 'C:\Program Files\eSpeak NG\espeak-ng.exe'
```

- If those commands don't work you may have to add the environment variables manually.
- You can add them to system variables like this picture. If you are unsure how to do this... google "how to set environment variables"

![image](https://user-images.githubusercontent.com/101527472/216216742-45f96ff7-d9ad-4c32-8063-6ae93fc11ede.png)



   
## TTS Voice Wizard Instructions
- Follow the above installation instructions
- To use glados TTS for TTS Voice Wizard run this (it will need to be running in the background for Glados TTS to work in TTS Voice Wizard)
- open console
- Change Directory or "cd" into the correct folder with engine-TTSVoiceWizard.py in it, here is an example:

```console
cd C:\Users\<NAME>\Downloads\glados-tts-voice-wizard-main\glados-tts-voice-wizard-main
```
- Run the python script
```console
python engine-TTSVoiceWizard.py
```
Note you will have to have this script running in the background whenever you wanna use the glados voice. 
**Becareful sharing screen for help, when the script is successfully run it will show your ip address with the port being used**

## Troubleshooting
- If you get an import error for something related to pydantics do ``pip install pydantic==1.10.11``
