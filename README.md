# Cryptography 

## Benefits:
- confidentiality
- integrity 
- authenticity
- access control

## Costs:
- availability
- performance
- complexity
- resource-intensiveness
- access control & key management
- operational & maintenance costs
- new hardware, employees, processes

## Risks:
- false sense of security
- no alternatives

## Deployment Requirements:
- threat modeling & use cases
- technical, administrative, maintenance, operational aspects
- fundamentals of cryptography
- training

## Components
- randomness source
- algorithms
- cryptographic keys
- key distribution

## Randomness
- statistically uniformly distributed
- independent of predecessor and successor
- generated from non-deterministic source (hardware RNG)
- pseudo-RNG used instead of hardware RNG
- pseudo-RNG use critical seeds(numbers/vectors) as source of entropy
- best high-entropy seed source: hardware RNG
- next best seed source: OS pseudo-random device drivers 
- worst seed source: software entropy source

## Flawed RNGs lead to
- compromised security
- predictable keys
- hackable connections
- kernel exploits 

## Terminology
 - Deterministic: a system/process that produces same/predictable output for given/variable initial state
 - Probabilistic: s system/process that produces non-deterministic output when initial state is known
 - Entropy: a measure of disorder (randomness)
 - Random Number: a number, where sequence of such #s are uniform and independent
 - True Random Number: a random number generated from non-deterministic source  
 - True RNG: a hardware RNG that produces True random number
 - Hardware RNG: a device that generates random numbers from physical processes, that are unpredictable
   high entropy sources, and extracts statistically uniformly distributed random numbers.
 - Pseudorandom number: a number whose properties closely aproximate the properties of true random numbers
 - Cryptographically Secure Pseudo RNG: a Pseudo-RNG using seed source of high entropy, that produce unpredictable 
   pseudorandom numbers, 
 - Seed: a number/vector used to initialize Pseudo RNG

## Algorithms:

### 1. Hash function
- maps data of arbitrary size to a bit-string of fixed size (hash)
- i.e.: converts input of any size to shorter fixed-length result
- deterministic: same input yields the same output

#### Cryptographic Hash Function:
- adds security features to typical hash function
- one-way function: function infeasible to invert
- produces output from which producing source is not feasible.
- collision-free: no two input hashes map to the same output hash.  

### 2. Cipher
- used for Encryption and Decryption
- Keys must be secure
- Symmetric cipher:  uses 1 key for Encryption/Decryption
- Asymmetric cipher: uses 2 related keys Encryption/Decryption

### 3. Encoder
- transforms data from formatA to formatB (e.g.: binary->text)
- doesn't provide security

### Usage:
- Pseudo-Random Number Generators
- Create/manage Security Keys
- Create/verify Message Authentication Code 
- Create/verify Digital Signature
- Create/verify Digital Certificate

## Cryptographic Keys
- used for lock(encrypt) or unlock(decrypt) data
	
### 1. Symmetric key
- usage: ciphers, msg-auth-codes
- one key used for encrypt/decrypt
- must remain secret
	
	
### 2. Asymmetric key
- usage: ciphers, digital signatures
- pair of related keys: public & private

#### 2.1. Public key
- publicly distributed
- used by public:
  - to encrypt plaintext (confidentiality)
  - to verify digital-signature (authenticity)

#### 2.2. Private key
- must remain secret 
- used only by owner:
  - to decrypt ciphertext (confidentiality)
  - to create digital-signature (authenticity)

### Key Distribution Problem: Symmetric keys
- symmetric key is a secret between 2 parties
- in standard security model:
  - 2 people, share 1 symmetric/secret key
  - 3 people, share 3 symmetric/secret keys
  - n people, share n(n-1)/2 keys (almost n^2)

### Key Distribution: Asymmetric keys
- public keys can be freely distributed
- 2 common means of key distribution
  - out-of-band distibution of public key fingerprints
  - digital certificates

### Public Key Fingerprint
- short sequence of chars used to authenticate a public key
- hash of public key + identity information
- created by key owner
- distributed out-of-band (e.g. IM, phone call, mem-stick)

### Digital Certificate 
- proves ownership of public-private key-pair
- verifies authenticity of public key
- created by trusted 3rd party based on info provided by key owner
- consists of, e.g.:
  - public-key: ABCD 1234 XYZW 5679
  - key owner: Bob Marley
  - key issuer: Trent Inc.
  - expiry date: Dec-10-2020
  - digital signature: TRENT!
