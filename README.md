# onnxruntime-cpp-lib

## How to build:

Follow [this guide](https://onnxruntime.ai/docs/build/inferencing.html) to build the onnxruntime library. If building inside a docker container add the flag `--allow_running_as_root` to the `./build.sh` command.

Then inside the root of this repository run:

```bash
cmake --install build/Linux/RelWithDebInfo/ --prefix "/home/onnxruntime/onnx-install/"
```
