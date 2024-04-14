# LocalChatLLM-edu

此项目基于 [LocalChatLLM](https://github.com/Gloridust/LocalChatLLM)，旨在通过开箱即用的本地化离线自然语言语音交互形式，实现儿童陪伴聊天早教等功能。

## 主要技术栈

- [x] Python  
- [x] ollama  
- [x] qwen
- [x] whisper  
- [x] pyttsx3  

## 功能实现

- [x] LLM自然语言对话 - ollama|qwen  
- [x] 语音输入 - whisper  
- [x] 语音合成 - pyttsx3
- [ ] 大模型实现自然语言合成
- [ ] 语音唤醒
- [ ] 自动结束录音 (静音检测)
- [ ] 局域网分布式运行

## 部署

1. clone 本仓库：

```bash
git clone https://github.com/Gloridust/LocalChatLLM-edu.git
cd ./LocalChatLLM-edu
```

2. 从官网安装 [ollama](https://ollama.com/download)

3. 安装Python依赖库：

```python
pip install -r requirements.txt
```

如果出现异常，首先尝试一步一步安装，检查哪一步出问题了：

```python
pip install ollama
pip install pyaudio
pip install pydub
pip install ffmpeg
pip install pyttsx3
pip install openai-whisper
```

参考 [Openai-Whisper](https://github.com/openai/whisper?tab=readme-ov-file#setup) 的官方文档，你需要根据不同的系统用以下命令安装ffmpeg：

```shell
# on Ubuntu or Debian
sudo apt update && sudo apt install ffmpeg

# on Arch Linux
sudo pacman -S ffmpeg

# on MacOS using Homebrew (https://brew.sh/)
brew install ffmpeg

# on Windows using Chocolatey (https://chocolatey.org/)
choco install ffmpeg

# on Windows using Scoop (https://scoop.sh/)
scoop install ffmpeg
```

如果您在上述 'pip install' 命令中看到安装错误，请按安装 Rust 开发环境。此外，您可能需要配置 PATH 环境变量，例如 'export PATH="$HOME/.cargo/bin:$PATH"' 。如果没有名为 "setuptools_rust "的模块，安装失败，则需要先安装 'setuptools_rust' :

```bash
pip install setuptools-rust
```

4. 拉取定制模型：

```bash
ollama create localchatllm-edu -f ./modelfile_cn
```

5. 初始化并尝试运行whisper：

```bash
whisper audio.wav --model base
```

大功告成！

## 运行

```bash
python start.py
```

程序录音5秒钟，然后等待生成回答。在朗读完生成的回答后，会再次进入录音状态，以此循环。

## 鸣谢

- [YGeeker](https://github.com/ygeeker)
- [OpenAI-Whisper](https://github.com/openai/whisper)
- [Ollama](https://github.com/ollama/ollama-python)
- [Qwen](https://huggingface.co/Qwen)
- [Gemma](https://huggingface.co/Qwen)