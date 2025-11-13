![](/pic.png)

```
mkdir llamacpp && cd llamacpp
curl https://api.github.com/repos/ggml-org/llama.cpp/releases/latest \
	| grep -Eo 'https://api.github.com/repos/ggml-org/llama.cpp/tarball/[^"]+' \
	| xargs curl -L \
	| tar -xz --strip-components 1
curl https://raw.githubusercontent.com/openingnow/chat/refs/heads/main/index.html \
	| gzip > tools/server/public/index.html.gz
cmake -B build
cmake --build build --config Release --target llama-server

...

llama-server -m model.gguf
```
