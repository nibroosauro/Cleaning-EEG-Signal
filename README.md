# EEG Data Preprocessing 💡🧠

Welcome to my EEG Data Cleaning project! Inspired by the awesome [G0rella](https://g0rella.github.io/gorella_mwn/preprocessing_eeg.html), this repo helps clean and visualize EEG signals from .edf files. 🧠✨ I’ve laid out the process, including the steps I took to make the data less noisy and more readable. It's super helpful for anyone working with EEG signals or neuro-research.

## What's Happening in This Repo?

I took a raw EEG dataset from opendataset [MNE Library](https://mne.tools/dev/documentation/datasets.html#datasets), cleaned it up, and applied techniques like filtering noise, downsampling, referencing, and even using ICA (Independent Component Analysis) to untangle brain activity signals. Here's what I did, step-by-step:

### 1. Load the EEG data 📂
I load the EEG data from an .edf file, a common format for bio-signals. Why `.edf`? It's because the European Data Format (EDF) is like the MP3 of bio-signals. It's simple, standardized, and packs a ton of signal info into a compact file. EEG often uses this format because it's great for storing time-series data with detailed metadata.

### 2. Visualize the raw data 👀
Raw EEG data can look like a big mess of squiggly lines. To make sense of it, I first plotted the raw signals to understand what I’m dealing with.

### 3. Referencing the signal 🎛️
Referencing is like giving context to the EEG signals. It involves subtracting a common reference signal from all channels to reduce noise. I used average referencing, which uses the mean signal across all electrodes as a reference. The result? A clearer signal, free from random noise!

### 4. Visualizing the Power Spectrum Density (PSD) 📊
PSD shows how the power (or strength) of the EEG signal is distributed across different frequencies. This is crucial because different brain activities happen at different frequencies. Think of PSD like the vibe check of your brainwaves — is it all chill delta waves or crazy high-frequency noise?

### 5. Filtering out noise 🔇
Next up, I applied filters to get rid of unwanted frequencies — basically cleaning out any static or "noise" that messes with the brainwave readings. I kept the important stuff like alpha, beta, and theta waves, and ditched the junk.

### 6. Downsampling + Nyquist Rate ⚖️📉
Ever wonder why we downsample? It’s like resizing an image so it's easier to work with, but for EEG data. Downsampling reduces the number of data points without losing crucial information. According to the **Nyquist Theorem**, we need to sample at least twice the highest frequency present in the signal. This makes sure no information is lost, and we don’t mess up the data by oversampling.

### 7. Data Visualization after Preprocessing 🎨
Once the noise was filtered and the data was downsampled, I visualized it again to compare it to the raw data. Cleaner, smoother, and more informative signals make for a better EEG analysis!

### 8. Handling bad channels (Interpolation) 🔄
Bad channels happen when one or more electrodes aren’t picking up the signal properly. Instead of ignoring them, I used **interpolation**, which means estimating what the bad channel should’ve been recording by using the surrounding channels' signals. Basically, it’s like filling in the blanks for brainwave activity.

### 9. Independent Component Analysis (ICA) 🧩
ICA is a super cool math trick that helps isolate the different sources of brain activity, solving what’s called the **cocktail party problem**. Imagine you’re at a party, and you want to listen to one convo in a noisy room. ICA helps pick out the individual “voices” in EEG data, like separating brain signals from eye blinks, muscle activity, or external noise.

---

### Shout-out 🙌
Big thanks to [G0rella's EEG Preprocessing project](https://g0rella.github.io/gorella_mwn/preprocessing_eeg.html) for the inspiration! 🙏 Make sure to check out the original for more detailed steps and concepts.

---

That's it! Feel free to explore the scripts in this repo and see how these steps make raw EEG data much cleaner and more usable for analysis. 🧠🚀
