# TensorFlow Custom Op

## Build Example zero_out Op (CPU only)

Clone the repository.

```bash
git clone https://github.com/tensorflow/custom-op.git
cd custom-op
```

## Build PIP Package

You can build the pip package with make.

```bash
  make zero_out_pip_pkg
```

## Install and Test PIP Package

Once the pip package has been built, you can install it with,

```bash
pip3 install artifacts/*.whl
```

Then test out the pip package

```bash
cd ..
python3 -c "import tensorflow as tf;import tensorflow_zero_out;print(tensorflow_zero_out.zero_out([[1,2], [3,4]]))"

```

And you should see the op zeroed out all input elements except the first one:

```bash
[[1 0]
 [0 0]]
```