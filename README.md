# TensorFlow Custom Op

## Build Example zero_out Op (CPU only)

Clone the repository.

```bash
git clone https://github.com/tensorflow/custom-op.git
cd custom-op
```

### Build PIP Package

You can build the pip package with make.

```bash
  make -f Makefile.puhti zero_out_pip_pkg
```

### Install and Test PIP Package

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

## Build Example time_two Op (GPU only on Puhti)

Clone the repository.

```bash
git clone https://github.com/tensorflow/custom-op.git
cd custom-op
```

### Load module

Load module,

```bash
ml tensorflow/2.12
```

Set env,

```bash
export SINGULARITY_BIND=$PWD
```

Run shell within the container

```bash
singularity shell $SING_IMAGE
```

Build the op with make,

```bash
make -f Makefile.puhti time_two_op
```

Test the op,

```bash
make -f Makefile.puhti time_two_test
```

## Build Example time_two Op (GPU only on Lumi)

Clone the repository.

```bash
git clone https://github.com/tensorflow/custom-op.git
cd custom-op
```

### Load module

Load module,

```bash
module use /appl/local/csc/modulefiles/
ml tensorflow/2.12
```

Set env,

```bash
export SINGULARITY_BIND=$PWD
```

Run shell within the container

```bash
singularity shell $SING_IMAGE
```

Build the op with make,

```bash
make -f Makefile.lumi time_two_op
```

Test the op,

```bash
make -f Makefile.lumi time_two_test
```
