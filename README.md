Minimal frontend for [llama.cpp](https://github.com/ggml-org/llama.cpp)

![](/pic.png)

Installation guide
```
mkdir llamacpp && cd llamacpp
curl https://api.github.com/repos/ggml-org/llama.cpp/releases/latest | grep -Eo 'https://api.github.com/repos/ggml-org/llama.cpp/tarball/[^"]+' | xargs curl -L | tar -xz --strip-components 1
curl https://raw.githubusercontent.com/openingnow/llamacpp-frontend/refs/heads/main/index.html | gzip > tools/server/public/index.html.gz
cmake -B build -DBUILD_SHARED_LIBS=OFF
cmake --build build --config Release -j 4 --target llama-server
cp build/bin/llama-server ~/path
cd ../
rm -rf llamacpp
```
