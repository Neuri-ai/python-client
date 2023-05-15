## Getting Started

To get started with the Neuri Python Client Library, you need to first install the library using `pip`:

```bash
pip install neuri
```
#### Import and initialize the library

```python
import neuri

config = {
    "service": "translate",
    "lang": "en",
    "temperature": 0.5,
    "api_key": "YOUR_API_KEY_HERE",
    "translate_to": "es" # optional
}

client = neuri.initialize_client(config)
```

### Use services

The Neuri Client Library currently supports three services: `audio_file`, `audio_url`, and `text`. Each service has its own set of parameters and returns a JSON containing the results of the processing.

- **`neuri.audio_file()`** [`Audio File`](#audio_file)
- **`neuri.audio_url()`** [`Audio URL`](#audio_url)
- **`neuri.text()`** [`Text`](#text)

## Audio File

Process audio files stored locally on your system using the audio_file service.

```python
result = client.audio_file(file_path=[
    os.path.join(os.path.dirname(__file__), "examples/girl_phone_call.wav"),
    os.path.join(os.path.dirname(__file__), "examples/noise_man_question.wav")
])
```

Replace the file paths in the `file_path` list with the actual paths to your audio files. The `audio_file` service will process the audio files and return the results in a JSON format.

## Audio URL

Process audio files from a remote URL using the `audio_url` service.

```python
result = client.audio_url(url="https://neuri-storage.s3.amazonaws.com/public_data/girl_phone_call.wav?AWSAccessKeyId=AKIAQFECGXRQOTIJ2FUV&Signature=GjrMz1NkMtQgFd0etJUCiQg4WNI%3D&Expires=1995267608")
```

Replace the file paths in the `url` list with the actual paths to your audio files. The `audio_url` service will process the audio files and return the results in a JSON format.


## Text

Process text using the text service.

```python
result = client.text(text="Hello, my name is John Doe")
```
Replace the `text` parameter with the actual text you want to process. The text service will analyze the text and return the results in a JSON format.