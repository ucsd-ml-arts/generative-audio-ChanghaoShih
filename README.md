# Project 3 Generative Audio

Changhao Shi, cshi@ucsd.edu

## Abstract

In this project I produce sounds from real neural signal recording of the brain. 
The basic idea is to compose a seed for midi generation with these neural signal, and use a pretrained deep network to carry on.
First, I count the spike for each neuron with a 10 ms time bin.
Then, I sum this multi-channel spike counts into 1-dimensional to get the spike counts of this neural population.
These spike counts are converted into pitches by adding a constant bias 60 to map them into reasonable range.
As the relative value of the counts remain the same, the larger the spike count is the higher the pitch is.
Using this seed, PerformanceRNN can help me generate longer piece of midi music. 
These procedures are performed on the baseline (inactive) stage and the planning (active) stage of the neural signals respectively.
I expect to get some difference in terms of the 'active level' corresponding to the real 'active level'
Instead of using default value of 1, the temperature is set to 0.7 so that we can have a clearer impression of the influences of the seed by reducing the randomness of sampling.

In the future, we can use some specific neural signals with oscillation to generate music, which is more rhythmic than this one.
Even further, we can record the neural signal of one listening or thinking about a piece of music, and try to recover that music from neural signals.

## Model/Data

- trained models: PerformanceRNN

    In this project, I use a pretrained PerformanceRNN model downloaded from the Magenta website.
    The version I use is the 'performance with dynamics'
    The model will be downloaded when running the python notebook file.

- training data: real ECoG signals

    The source data I use is some ECoG signal recorded from a monkey, provided by Professor Vikash Gilja in ECE209 (Statistical learning for biosignal processing). 
    The 97-channel ECoG signals are recorded for 700 ms, during which period the monkey is asked to reach for a target after seeing a cue.
    The data is stored in a 97*700 matrix, where each entry is 1 or 0 depending on the appearance of a neural spike in that milisecond.

## Code

- Jupyter notebooks: generative_code.ipynb

## Results

- `baseline.mid`: midi generation of baseline stage neural recording
- `planning.mid`: midi generation of planning stage neural recording

Listenning to the music, we can find that the midi generation from the planning stage is somehow indeed more 'active' than baseline stage.
PerformanceRNN composes more variation on the strength of the hits in planning generation while it composes almost light hits in baseline generation.
Midi generation from baseline stage is more flat while the generation from planning stage is more emotional.

## Technical Notes
 
- Note that the seed melody is hard-coded into the notebook file. To use different seed, please copy it into the corresponding position.

## Reference

None
