# research-bounties

The following are a list of unsolved problems or problems being outsourced for
bounties.

## Problems

These problems are in no general order or impact. If you think a bounty should
be several smaller bounties, please open an issue with a brief justification
and let's start a dialogue.

### AI

**NOTE: All of the given problems (where applicable) should be completed using one of the following 
datasets (or similar at different sampling rates)- the more sensors in use, the better. The models
must be efficient enough to train over a *reasonable* time-window (ideally 24 hours of data to identify a user at .8 confidence), 
locally, on a smartphone. All sensor data will be local to the phone and training models must be online to adapt to user behavior.**

* [ExtraSensory](http://extrasensory.ucsd.edu/)
* [Mobile Sensor Daily Activity Data Forensics](https://ieee-dataport.org/documents/mobile-sensor-daily-activity-data-forensics)

#### Generative sensor datasets

Given publicly available sensor data, create a generative adversarial network that can generate realistic user data at 
variable sampling rates. This problem solves combining columns other sets are missing and limitations of a dataset not 
being a long-enough time-frame, too low of a sampling frequency in one dataset, increasing sensor noise/variability, 
missing sensor or datapoints from other datasets, and others.

The GAN should be able to generate/discriminate a sensor timestamp and be within a sane confidence of real user behavior
from existing datasets. i.e. the barometer pressure shouldn't be deep sea levels.

#### User position detection

Given a user's daily activity on as many sensors as possible for useful classification, detect their bodily positioning
and motion.

Classifications generalization:

- Prone
- Standing
- Walking
- Sitting
- ...

#### Phone placement detection

Given a user's daily activity on as many sensors as possible for useful classification, detect their phone positioning.

Classifications generalization:

- In hand
- In front pants pocket
- In back pants pocket
- In shirt pocket
- Being sat on
- ...

#### Voice identification

**NOTE: This dataset will need to be collected and/or located.**

Given a fourier decomposition of intermittent soundwaves, identify a user by their unique wave decomposition.
Submission should have a threshold confidence for identifying unknown users (i.e. below .7 confidence is an
unidentified user).

Classifications:

- User ID

#### Grasp identification

This is one of those crazy ideas.

Using as many sensors as relevant to discern the "unique phone grip", correctly identify a user by the way
they hold their phone. Submission should have a threshold confidence for identifying unknown users (i.e. 
below .7 confidence is an unidentified user).

Classifications:

- User ID

#### Keystroke identification

Given the way a user enters keystrokes, identify the user. Submission should have a threshold confidence for
identifying unknown users (i.e. below .7 confidence is an unidentified user).

Classificationis:

- User ID

#### Swipe identification

Given the a user swipes their touchscreen, identify the user. Submission should have a threshold confidence
for identifying unknown users (i.e. below .7 confidence is an unidentified user).

#### Neuroevolution to find meaningful sensors and datapoints

Given a grab-bag of attributes for identifying a user, wrap a neural network in a genetic algorithm to 
try training on different permutations of available data to find what can classify and what can't for 
novel methods of identification.

### Cryptology (and more AI within, but not AI-specific problems)

The following are unsolved problems for the scope of deadman.wtf

#### Steganography

##### Watermarking ML models

In order to identify if a model was stolen, create a steganographic means of embedding a signature
into the weights of a model. This is for attribution and inspired by Microsoft's ImageDNA. 

1. Embedding a "magic input" that produces a "magic output".
2. If homomorphic networks (see cryptography) have already been solved, embed a cryptographic signature
into the means of encryption.

#### Cryptography

##### Homomorphic-encrypted ML networks

Use homomorphic encryption on the weights of the network to protect the model and operate on encrypted 
data to make leaking impossible unless a key from the TPM of the device is able to be exfiltrated.

##### Adapt HTTP signature auth to use a zero-knowledge proof

To reduce complexity/payload size, devise an authentication scheme where we can simply prove we know 
a secret without revealing anything about the secret via proof. Submission should include a threat 
model and mitigations for those threats that became a part of the design.


