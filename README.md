# CMU Sphinx Models
The repository of acoustic and language models, and the tools to download raw data and train them. Currently only for Catalan.

The models are trained with *sphinxtrain 5prealpha*. You can find further details in our [webpage](https://collectivat.cat/asr) and in our [wiki](https://github.com/collectivat/cmusphinx-models/wiki). If you just want to download the latest acoustic and language models in Catalan you can find them [here](https://cloud.laklak.eu/s/4o2b5MrHckMYCXo).

## git clone

Once you have complete the standard `git clone` you also need `git-lfs`.

The first time you need to:

```
sudo apt-get install git-lfs
git lfs install
```

and then every time:

```
git lfs pull
```

## Requirements
For basic setup, one needs to install *PocketSphinx*. For Debian systems:

```
sudo apt-get install pocketsphinx
```

You can also compile directly from the [releases](https://cmusphinx.github.io/wiki/download/), or from the source code in [github](https://github.com/cmusphinx) or [sourceforge](https://sourceforge.net/p/cmusphinx/code/HEAD/tree/). The installation steps are explained in the official [CMU Sphinx tutorials](https://cmusphinx.github.io/wiki/tutorialpocketsphinx/).

The test scripts are tested for Python 3.5.2, and in order for them to run, `pocketsphinx` and `SpeechRecognition` modules are needed. You can install them by:
```
sudo apt-get install swig
sudo apt-get install libpulse-dev
pip3 install -r requirements.txt
```

## Catalan
### Models

All the files necessary for pocketsphinx, i.e. the language model, phonetic dictionary and the acoustic models are in `ca-es` directory. The model files are:

```
ca-es
 ├─ pronounciation.dict       (Phonetic dictionary)
 ├─ language-model.lm.bin     (Language model)
 └─ acoustic-model            (Acoustic model)
    ├─ feat.params
    ├─ mdef
    ├─ means
    ├─ mixture_weights
    ├─ noisdict
    ├─ transition_matrices
    └─ variances
```

In order to test the models, simply execute:
```
$ python scripts/decode_from_file.py
la seva abraçada havia estat una batalla el clímax una victòria
```

### Corpus
The training data consists of 240 hours of Catalan Public television (TV3Parla corpus) and 320 hours of recording from Catalan Parliament ([Parlament de Catalunya](https://www.parlament.cat/)) plenary sessions (ParlamentParla corpus). The TV3 data was prepared with the support of [Softcatalà](https://www.softcatala.org/), the Parlament data was prepared with the support of the [Culture Department](http://cultura.gencat.cat/) of the Catalan autonomous government.

For further details and the download links of the data, please visit our [resurces for speech technologies](https://collectivat.cat/asr) page.

---

Part of this project, specifically the ParlamentParla corpus and training of current acoustic models, was possible thanks to the support of the [Culture Department](http://cultura.gencat.cat/) of the Catalan autonomous government.

<img src="/img/logo_generalitat.png" width="400"/>
