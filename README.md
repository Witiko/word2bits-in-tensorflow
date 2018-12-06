# Word2Bits in TensorFlow

This series of notebooks seeks to reproduce the results of the [Word2Bits
paper][1] (Lam, 2018) by applying the least necessary amount of changes to the
[basic word2vec example][2] from a [TensorFlow word tutorial][3].

## Getting Started

These instructions will get you a copy of the project up and running on your
local machine.

### Prerequisites

You need the following tools for the installation:

- Git

### Installing

Install Jupyter and the necessary Python packages as follows:

```
$ pip install jupyter
$ pip install -r requirements.txt
```

## Jupyter Notebooks

The repository contains the following Jupyter notebooks:

- [`word2vec_basic.ipynb`](word2vec_basic.ipynb) – The [basic word2vec
  example][2] with no substantial changes.

- [`word2vec.ipynb`](word2vec.ipynb) – The [basic word2vec example][2] with changes to the
  learning rate, dictionary size, negative sampling, and context size according
  to the [Word2Bits paper][1] (Lam, 2018). *Known* differences between the code
  in the notebook and the paper are documented.

- [`word2bits.ipynb`](word2bits.ipynb) – The [basic word2vec example][2] with changes to the
  learning rate, dictionary size, negative sampling, and context size according
  to the [Word2Bits paper][1] (Lam, 2018). Quantization of the input word
  embeddings is also implemented. *Known* differences between the code in the
  notebook and the paper are documented.

## Vector Embeddings

The repository contains *compressed* and *split* vector embeddings produced by
the Jupyter notebook in the format accepted by the the [Word2Bits paper][1]
(Lam, 2018) [implementation][4].

To unsplit and decompress the vector embeddings for the notebook
`word2bits.ipynb`, run the following command:

```
$ cat word2bits.nonbin.gz.* | gzip -d > word2bits.nonbin
```

Proceed analogously for the other embeddings.

 [1]: https://arxiv.org/abs/1803.05651 (Word2Bits-Quantized Word Vectors)
 [2]: https://github.com/tensorflow/tensorflow/blob/master/tensorflow/examples/tutorials/word2vec/word2vec_basic.py
 [3]: https://www.tensorflow.org/tutorials/representation/word2vec (Vector Representations of Words)
 [4]: https://github.com/stefanik12/Word2Bits/blob/master/src/compute-accuracy.c
