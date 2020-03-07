# Hyperspherical Variational Auto-Encoders
### Tensorflow implementation of Hyperspherical Variational Auto-Encoders

## Overview
This library contains a Tensorflow implementation of the hyperspherical variational auto-encoder, or S-VAE, as presented in [[1]](#citation)(http://arxiv.org/abs/1804.00891). Check also our blogpost (https://nicola-decao.github.io/s-vae).

* You do not use Tensorflow? Take a look [here](https://github.com/nicola-decao/s-vae-pytorch) for a **pytorch** implementation!

## Dependencies

* **python>=3.6**
* **tensorflow>=1.7.0**: https://tensorflow.org
* **scipy**: https://scipy.org

## Installation

To install, run

```bash
$ python setup.py install
```

## Structure
* [distributions](https://github.com/nicola-decao/s-vae-tf/tree/master/hyperspherical_vae/distributions): Tensorflow implementation of the von Mises-Fisher and hyperspherical Uniform distributions. Both inherit from `tf.distributions.Distribution`.
* [ops](https://github.com/nicola-decao/s-vae-tf/tree/master/hyperspherical_vae/ops): Low-level operations used for computing the exponentially scaled modified Bessel function of the first kind and its derivative.
* [examples](https://github.com/nicola-decao/s-vae-tf/tree/master/examples): Example code for using the library within a Tensorflow project.

## Usage
Please have a look into the [examples folder](https://github.com/nicola-decao/s-vae-tf/tree/master/examples). We adapted our implementation to follow the structure of the recently proposed [Tensorflow Distribution library](https://www.tensorflow.org/api_docs/python/tf/distributions/Distribution), ([Dillon et al, 2017](https://arxiv.org/abs/1711.10604)).

Please cite [[1](#citation)] in your work when using this library in your experiments.

## Sampling von Mises-Fisher
To sample the von Mises-Fisher distribution we follow the rejection sampling procedure as outlined by [Ulrich, 1984](http://www.jstor.org/stable/2347441?seq=1#page_scan_tab_contents). This simulation pipeline is visualised below:

<p align="center">
  <img src="https://i.imgur.com/aK1ze0z.png" alt="blog toy1"/>
</p>

_Note that as ![](http://latex.codecogs.com/svg.latex?%5Comega) is a scalar, this approach does not suffer from the curse of dimensionality. For the final transformation, ![](http://latex.codecogs.com/svg.latex?U%28%5Cmathbf%7Bz%7D%27%3B%5Cmu%29), a [Householder reflection](https://en.wikipedia.org/wiki/Householder_transformation) is utilized._

## Feedback
For questions and comments, feel free to contact [Nicola De Cao](mailto:nicola.decao@gmail.com).

## License
MIT

## Citation
```
[1] Davidson, T. R., Falorsi, L., De Cao, N., Kipf, T.,
and Tomczak, J. M. (2018). Hyperspherical Variational
Auto-Encoders. 34th Conference on Uncertainty in Artificial Intelligence (UAI-18).
```

BibTeX format:
```
@article{s-vae18,
  title={Hyperspherical Variational Auto-Encoders},
  author={Davidson, Tim R. and
          Falorsi, Luca and
          De Cao, Nicola and
          Kipf, Thomas and
          Tomczak, Jakub M.},
  journal={34th Conference on Uncertainty in Artificial Intelligence (UAI-18)},
  year={2018}
}
```
