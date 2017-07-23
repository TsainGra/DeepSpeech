# DeepSpeech
An end-to-end model for Automatic Speech Recognition(ASR) on a small VoxForge dataset. It uses a CTC loss function and a single layer B-LSTM Network. The training accuracy is around 87% and to increase the validation accuracy a much deeper network with much more data is needed.

Start by first running the "download_voxforge_data.py" this downloads the data from the VoxForge repository for the specific speaker "Aaron". More data can be downloaded by making minor changes in the script.

Once we have the data use "generate_voxforge_txt_files.py" to extract the transcripts of the VoxForge dataset in the folder.

Now, run the "generate_voxforge_training_data.py" to get the input features for speech recognition, Mel Frequency Cepstral Coefficients (MFCCs) are extracted. They are assembled into a batched format with the target character level annotations for subsequent training

The file "train_ctc_voxforge.py" uses a Single layer bidirectional LSTM network to predict the transcriptions from the audio features. Every 10 epochs, an example batch is decoded and printed for comparision with the target.
