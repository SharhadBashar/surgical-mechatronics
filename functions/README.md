# Reverse channel samples in 1D array
We have a 1D array `float64 arr[60]` being used to store voltage values from a DAQ. The array is populated as such:
 
    10 SAMPLES_PER_CHANNEL, 6 CHANNELS, grouped by channel
    transducer_0    transducer_1   ...  transducer_6
    [0, 1 ..., 9,   10, 11 ..., 19 ...  50, 51 ..., 59]

We would like to reverse the order of the samples in each channel resulting in:

    transducer_0    transducer_1   ...  transducer_6
    [9, 8 ..., 0,   19, 18 ..., 10 ...  59, 58 ..., 50]

This operation must be done in place (no additional storage structure). We would also like to take advantage of the std:reverse() function.

# Function header
    ReverseChannelSamples(float64* arr, unsigned int size);