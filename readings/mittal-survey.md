### Contribution

- Techniques for characterizing and improving **resiliency** of DNNs

### Scope of Survey

- Only work that focus on reliablity issues on NNs
- Implications on DNN's performance, energy efficiency, and security
- The survey assumes two main approaches to **fault injection**:
  1. Software-based fault injection
  2. Physics-based fault injection due to radiation (comis background radiation)

### Key Observations

- Some bit error rate (BER) is OK if it's below threshold. DNNs accuracy usually drops signifcantly above threshold
- Max-pooling and ReLU only masks faults that result in negative values
- FC and CONV layers are vulnerable to faults as they propagate fault to entire output (CONV is a bit safer due to ReLU layers)
- Reduced precision (float16 or float8) reduces chance of an attack (since footprint of attack-able bits are reduced), but LSB corruption is more severe.
- For VGG16 and LeNet5, *quantization* of weights work better than pruning to improve resiliency

