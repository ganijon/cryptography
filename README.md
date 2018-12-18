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
- false sense of security
- there are no alternatives to cryptography

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

1. Hash functions
- converts any size of source -> shorter fixed length output
- Cryptographically Secure Hash Function:
	- produces output from which producing source is not feasible.
	- no two inputs produces the same result.  

2. Cipher
- used for Encryption and Decryption
- Keys must be secure
- Symmetric cipher:  uses 1 key for Encryption/Decryption
- Asymmetric cipher: uses 2 related keys Encryption/Decryption

3. Encoder
- transforms data from format-A -> format-B (e.g.: binary->text)
- doesn't provide security

### Usage:
- Pseudo-Random Number Generators
- Create/manage Security Keys
- Create/verify Message Authentication Code 
- Create/verify Digital Signature
- Create/verify Digital Certificate

## Cryptographic Keys
- used for lock(encrypt) or unlock(decrypt) data
	
1. Symmetric key
- usage: ciphers, msg-auth-codes
- one key used for encrypt/decrypt
- must remain secret
	
	
2. Asymmetric key
- usage: ciphers, dig-signatures
- pair of related keys: public & private
2.1. Public key
- publicly distributed
- used by public to encrypt plaintext / verify dig-signature
2.2. Private key
- must remain secret
- used only by its owner. 
- used to decrypt ciphertext / create dig-signature
 
