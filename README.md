# Workshop for Class 11


## 1. A few more things on high powered machines: using tmux (to create multiple sessions) and nvidia-smi (to check your GPU)

First, type:

```
tmux
```

to start a tmux session. From there, you do your normal training command (melody_rnn_train etc).

To detach:

```
control + b
```

then

```
d
```
to detach the session.

While we're detached, we can use nvidia-smi to check that the GPU is running. Nvidia-smi should be already built into your Paperspace environment. You can run it by typing:

```
nvidia-smi
```

You should see an ascii-image that shows that the GPU is running. If it is not running, it will say "No processes found".

To attach back to your tmux session, first list the available sessions:

```
tmux ls
```

Note the number of the session you want to attach to (for example, 0). Then type this to attach back to that session:

```
tmux attach-session -t 0
```

## 2. Intro to latent space models

Short presentation on latent space models and MusicVAE.

## 3. MusicVAE and intro to with Colab notebook
#### What MusicVAE is doing: allows you to generate melodies by interpolating between two MIDIs.

First, let's check out the basic Colab intro: [https://colab.research.google.com/notebooks/welcome.ipynb](https://colab.research.google.com/notebooks/welcome.ipynb)

Make sure you are using the GPU (go to Edit -> Notebook Settings to change this). For the record, Colab has limits on both GPU time and storage, so they are better for quick interaction than long-term training (at the moment).

Copy the [MusicVAE Colab notebook](https://colab.research.google.com/drive/1POmWhBoq_ECPCRZeH8R_oXtKTIjiXyWl) to your drive with the 'Copy to Drive' button. (This is very close to the original Magenta version, with a few lines changed to be able to download our final MIDI.)

We'll just be looking at the 16-bar melody models.

## 4. (If time, optional) Converting MIDIs to mp3

We might not get into this, but the code to convert your MIDI to an mp3 with a nicer-sounding soundfont is in the convert_to_mp3 folder. You can run the command by typing (change the MIDI file name if necessary):

```
./MIDI_to_mp3.sh interpolation.mid
```

You will need to install Fluidsynth and LAME to use this if your machine does not have them installed already.


## 5. Intro to Wavenet/NSynth

Short presentation on Wavent/NSynth.

## 6. Making your own sounds with NSynth

Copy the [NSynth Colab notebook](https://colab.research.google.com/notebooks/magenta/nsynth/nsynth.ipynb) to your Google drive with the 'Copy to Drive' button. 

## 7. Talk about training your own Wavenet

https://github.com/hollygrimm/wavenet-plath

## 8. Student Presentations


## Assignment

Your final projects are due next week! These should be well thought out projects containing at least *one minute* of generated audio. They can be related to anything we've learned in class, but should be different than other projects you presented (i.e. if your other two projects were related to data sonification, try to do something with machine learning generated melodies). 

## Additional Notes, Suggested Things to Do

* Don't be afraid to explore the other models we didn't get to in class! Working with them is very similar to what we did today, and each has its own walk-through: [https://github.com/tensorflow/magenta/tree/master/magenta/models](https://github.com/tensorflow/magenta/tree/master/magenta/models)

* You can look at the PolyphonyRNN model, which is very similar to MelodyRNN, but it generates polyphonic music (meaning it generates more than one note at a time).

* Also, you can hook these models up to a MIDI interface! [https://github.com/tensorflow/magenta/tree/master/magenta/interfaces/midi](https://github.com/tensorflow/magenta/tree/master/magenta/interfaces/midi)

* There are other Colab notebooks you can explore in the Seedbank:
[https://research.google.com/seedbank/](https://research.google.com/seedbank/). Check out the Audio Style Transfer or Piano Transcription notebooks.

