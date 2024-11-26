# Speech Denoising using Deep Learning
This work investigates speech denoising using three model architectures: a fully connected deep neural network, a 1D convolutional neural network (CNN), and a recurrent neural network (RNN).

Audio files are preprocessed using the Short-Time Fourier Transform (STFT) to generate spectrograms. In the first approach, which utilizes a fully connected deep network and subsequently a 1D CNN, the denoising process involves feeding the magnitude spectra of noisy test mixtures into the model to predict clean magnitude spectra. The denoised speech signal is then reconstructed by applying the inverse STFT. Early stopping is guided by the Signal-to-Noise Ratio (SNR), which compares the cleaned signal to the ground truth to evaluate the quality of denoising. For the 1D CNN, denoising is performed in the STFT magnitude domain, where convolutions operate exclusively along the frequency axis.

In the second approach, an RNN is employed to leverage the temporal structure inherent in audio signals. Training audio data is transformed into spectrograms, and the RNN processes sequences of 513-dimensional spectral frames to predict clean speech. The model is trained to estimate Ideal Binary Masks (IBMs), which serve as the target for the denoising task. The network's performance is assessed by calculating the average SNR across all validation audio signals.






