# Resources

Used to store large files and assets used in BaseRepo4 and other Emancro repos.

### `torch/`

This contains the patched wheel as well as .patch file used to create it for `torch==2.2.2`.

Steps to use the wheel in a monorepo with Bazel+Pipenv (based on https://github.com/jacksmith15/bazel-python-demo) -
1. Go to your monorepo directory, execute `pipenv install <link to raw .whl file from this repo>`
2. `bazel clean --expunge && bazel test //:test_torch_cuda` to check torch, CUDA and ultralytics work in a python script.

Notes:
The original torch wheel is from https://download.pytorch.org/whl/cu121/torch-2.2.2%2Bcu121-cp310-cp310-linux_x86_64.whl
and is patched using scripts/patcher.py at https://github.com/georgevreilly/torch21
