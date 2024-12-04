# onnxruntime-cpp-lib

## How to build

```bash
chown -R $USER:$USER /path/to/onnxruntime-cpp-lib
cd onnxruntime
git checkout #tag
git submodule update --init --recursive
```

Follow [this guide](https://onnxruntime.ai/docs/build/inferencing.html) to build the onnxruntime library, but replace `RelWithDebInfo` with `Release`. If building inside a docker container add the flag `--allow_running_as_root` to the `./build.sh` command.

```bash
# For Linux
./build.sh --config Release --build_shared_lib --parallel --compile_no_warning_as_error --skip_submodule_sync --allow_running_as_root
```

Then inside the root of the onnxruntime repository, run the following command to install the library to the specified path.

```bash
cmake --install build/Linux/Release/ --prefix "/root/onnxruntime-cpp-lib/onnxruntime-1.19.2-Linux-armv7l" 
```

Then use the following command to compress the library. Zip will break the symbolic links, so use tar instead.

```bash
tar -zcvf onnxruntime-1.19.2-Linux-armv7l.tar.gz onnxruntime-1.19.2-Linux-armv7l
```
