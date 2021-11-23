# audio_analysis
## Nathan Tansey

This project analyzed and utilized spectrograms as representations of sound. These were created using parts of Tim Sainburg's code so as to manually create spectrograms using STFT (short-time fourier transform) rather than use prebuilt packages and functions.

These projects use a fixed NFFT (non-uniform fast fourier transform). The research quickly reinforced the notions behind the Fourier uncertainty principle, in which there is a tradeoff between accurate frequency and accurate time within the representation. Sound files were tested by converting them into a spectrogram, and then inverting them back to a sound file to hear how much information had actually been stored in the spectrogram. These resulted in showing a higher NFFT gave more accurate frequency, but a loss in time. For the purposes of this research, the NFFT is fixed across the board. For each sound file, it may make more sense to either prioritize the time, or the frequency. Future research could involve an automatic adjustment to the NFFT accordingly.

The jupyter notebook 'CFLreverbRE' explores the use of Frederick Eberhardt's Causal Feature Learning python package: https://cfl.readthedocs.io/en/latest/index.html

This package works by creating cause and effect pairings between the given train data by using KMeans clustering techniques. The model then can be applied to test data. This was applied to spectrograms by exploring whether or not the package could function by creating a reverberant version of sound. This was attempted by creating a reverberant version of an original sound, and then training on the first half of each sound file, with the original sound labeled as the cause, and the reverberant version labeled as the effect. This was then applied to the second half of the cause sound file. Using the causal linkages from the training, these were used in conjunction with the test data so as to recreate a version of the reverberant data.

Included in the wav_files folder are various sound files which were used during the project and within the code.
