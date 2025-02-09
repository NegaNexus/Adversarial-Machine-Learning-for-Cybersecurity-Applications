# Adversarial Machine Learning for Cybersecurity Applications

This repository contains code for exploring generating adversarial examples for two different cybersecurity related datasets:
- **[KDD-Cup-99](https://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html)**: A network intrusion dataset consisting of PCAP records with 41 features. The training set contains 494,021 records the testing set contains 311,029 records.
- **[Ember](https://github.com/elastic/ember)**: A dataset containing vectorized malware and goodware Portable Executable files. Each record consists of 2,381 features. See [EMBER: An Open Dataset for Training Static PE Malware Machine Learning Models by Anderson, et al. (2018)](https://arxiv.org/abs/1804.04637) for details on the dataset and the vectorization scheme.

The Deep Learning models are all developed with [PyTorch](https://pytorch.org/) and [PyTorch Lightning](https://www.pytorchlightning.ai/). PyTorch Lightning is a great library which takes care much of the boilerplate code for training and building models. It is somewhat analogous to Keras with Tensorflow, but does not abstract away nearly as much as Keras does.

The code for generating adversarial examples is based on the [Adversarial Robustness Toolbox](https://adversarial-robustness-toolbox.org/).

This code was developed for [Dr Aleksander Vakanski](https://www.webpages.uidaho.edu/vakanski/)'s [CS 504: Adversarial Machine Learning](https://www.webpages.uidaho.edu/vakanski/CS_504.html) course taught at the University of Idaho.

# Structure

The repository contains two different [Jupyter Notebooks](https://jupyter.org/): 
- [The experiments on the KDD-Cup-99 dataset](https://github.com/NegaNexus/Adversarial-Machine-Learning-for-Cybersecurity-Applications/blob/aaa90a827682bd8d93604cc95aff5a29d7ee77b5/AML_Assignment_3_Part_1(1).ipynb) ([nbviewer](https://nbviewer.org/github/NegaNexus/Adversarial-Machine-Learning-for-Cybersecurity-Applications/blob/aaa90a827682bd8d93604cc95aff5a29d7ee77b5/AML_Assignment_3_Part_1%281%29.ipynb))
- [The experiments on the Ember dataset](https://github.com/NegaNexus/Adversarial-Machine-Learning-for-Cybersecurity-Applications/blob/aaa90a827682bd8d93604cc95aff5a29d7ee77b5/AML_Assignment_3_Part_2(1).ipynb) ([nbviewer](https://nbviewer.org/github/NegaNexus/Adversarial-Machine-Learning-for-Cybersecurity-Applications/blob/aaa90a827682bd8d93604cc95aff5a29d7ee77b5/AML_Assignment_3_Part_2%281%29.ipynb)).

In each notebook, white-box non-targeted adversarial attacks are generated for their respective Deep Learning models.

The adversarial attacks tested for each are:
- **Fast Gradient Sign Method** from [Explaining and Harnessing Adversarial Examples by Goodfellow et al. (2015)](https://arxiv.org/abs/1412.6572) using the [implementation](https://adversarial-robustness-toolbox.readthedocs.io/en/latest/modules/attacks/evasion.html#fast-gradient-method-fgm) in Adversarial Robustness Toolbox
- **Carlini and Wagner ℓ2** from [Towards Evaluating the Robustness of Neural Networks by Carlini and Wagner (2016)](https://arxiv.org/abs/1608.04644) using the [implementation](https://adversarial-robustness-toolbox.readthedocs.io/en/latest/modules/attacks/evasion.html#art.attacks.evasion.CarliniL2Method) in Adversarial Robustness Toolbox
- **DeepFool** from [DeepFool: a simple and accurate method to fool deep neural networks by Moosavi-Dezfooli et al (2015)](https://arxiv.org/abs/1511.04599) using the [implementation](https://adversarial-robustness-toolbox.readthedocs.io/en/latest/modules/attacks/evasion.html#art.attacks.evasion.DeepFool) in Adversarial Robustness Toolbox
- **Jacobian Saliency Map Attack (JSMA)** from [The Limitations of Deep Learning in Adversarial Settings by Papernot et al. (2015)](https://arxiv.org/abs/1511.07528) using the [implementation](https://adversarial-robustness-toolbox.readthedocs.io/en/latest/modules/attacks/evasion.html#jacobian-saliency-map-attack-jsma) in Adversarial Robustness Toolbox

These notebooks were developed and tested on [Google Colab](https://colab.research.google.com/). Alternatively, we have included a [requirements.txt](https://github.com/NegaNexus/Adversarial-Machine-Learning-for-Cybersecurity-Applications/blob/7b81cfea72d06595d552e61f75c5906b486512e0/requirements.txt) in case you would like to run the notebooks on other systems. *NOTE: The requirements.txt file was generated by running `pip freeze > requirements.txt`, so it has many superfluous packages that Google Colab comes preinstalled with at runtime, but it should be enough to get you started. It has not been tested, but should work, perhaps with a little bit of work.*
