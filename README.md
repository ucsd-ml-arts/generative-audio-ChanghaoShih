# Project 3 Generative Audio

Changhao Shi, cshi@ucsd.edu

## Abstract

In this project I produce sounds from real neural signal recording of the brain. 
The basic idea is to compose a seed for midi generation with these neural signal, and use a pretrained deep network to carry on.
I extract the spike counts for each neuron, then convert these spike counts into pitches: the larger the spike count is the higher the pitch is.
Using this seed, PerformanceRNN can help me generate longer piece of midi music. 

## Model/Data

Briefly describe the files that are included with your repository:
- trained models: PerformanceRNN
    In this project, I use a pretrained PerformanceRNN model downloaded from the Magenta website.
    The version I use is the 'performance with dynamics'
    The model will be downloaded when running the python notebook file.
- training data: real ECoG signals
    The source data I use is some ECoG signal recorded from a monkey, provided by Professor Vikash Gilja in ECE209 (Statistical learning for biosignal processing). 
    The 97-channel ECoG signals are recorded for 700 ms, during which period the monkey is asked to reach for a target after seeing a cue.
    The data is stored in a 97*700 matrix, where each entry is 1 or 0 depending on the appearance of a neural spike in that milisecond.

## Code

Your code for generating your project:
- Jupyter notebooks: generative_code.ipynb

## Results

Documentation of your results in an appropriate format, both links to files and a brief description of their contents:
- `.wav` files or `.mp4`
- `.midi` files
- musical scores
- ... some other form

## Technical Notes

Any implementation details or notes we need to repeat your work. 
- Does this code require other pip packages, software, etc?

## Reference

References to any papers, techniques, repositories you used:
- Papers
- Repositories
- Blog posts
