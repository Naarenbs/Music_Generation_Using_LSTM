# Music Generation Using LSTM

This project is an AI-based music generation model that uses Long Short-Term Memory (LSTM) recurrent neural networks to compose multi-instrumental MIDI music. It processes raw MIDI files to learn the patterns in pitch, step, and duration, and subsequently generates original compositions.

## Overview

The model learns from a collection of MIDI files and predicts the next notes (pitch, step, and duration) in a sequence. After training, it utilizes these predictions alongside a temperature-scaling mechanism to synthesize entirely new music tracks featuring multiple instruments (e.g., Acoustic Grand Piano, Violin, and Electric Bass).

## Features

- **MIDI Data Processing:** Extracts temporal and pitch data straight from `.mid` files using `pretty_midi`.
- **Custom LSTM Architecture:** Uses TensorFlow and Keras to train an LSTM model optimized with specific loss functions and weights for predicting `pitch`, `step`, and `duration`.
- **Audio Playback Integration:** Incorporates `fluidsynth` and `pyfluidsynth` to synthesize MIDI to raw audio for inline playback in Jupyter Environments.
- **Multi-Instrument Generation:** Generates comprehensive music sequences orchestrating different instruments into a single `multi_instrument_music.mid` output file.

## Requirements

The core dependencies for this project include:
- `python >= 3.7`
- `tensorflow`
- `numpy`
- `pandas`
- `pretty_midi`
- `pyfluidsynth`

Additionally, you need to install the system-level `fluidsynth` package for audio synthesis:
```bash
sudo apt install -y fluidsynth
```

## Usage

1. **Extract Data:** Ensure your dataset (e.g., `Music_Generation_Using_LSTM_Dataset.zip`) is extracted to a working directory containing `.mid` files.
2. **Train Model:** Run the cells in `Music_Generation_Using_LSTM(1).ipynb`. The model parses the data, builds sequence datasets, trains over multiple epochs, and saves the trained model as `saved_music_lstm_model.keras`.
3. **Generate Music:** During the generation phase, the predict function generates 500 iterative notes per specified instrument and compiles them into a comprehensive `.mid` file for download and listening.

## Model Saving

Upon completing training, the LSTM model automatically saves locally to `saved_music_lstm_model.keras` for future reuse without requiring retraining.