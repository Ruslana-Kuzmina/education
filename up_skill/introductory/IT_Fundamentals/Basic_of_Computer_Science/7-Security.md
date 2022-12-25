# Security

They are often divided into two groups of topics:

- Security at rest - means that the data is in a stable state: it is not being
  acted upon by any application and it is not being transmitted over the network.
- Security in transit - means that the data is being transmitted over the network.
  Password hashing, encryption, and secure communications are basic methods to
  achieve computer security.

## Passwords

A password is a string of characters used to confirm the identity of a user.

Several organizations have released various guidelines on strong passwords.
Most common advice is:

- A minimum password length should be 10
- Use lowercase and uppercase characters, numbers, and symbols
- Do not use the same password for different accounts
- Avoid dictionary words and any information which might be associated with the
  user (names, dates)

So far, we assumed that the attacker would try all possible combinations of symbols
to find the password. Such attacks are called **brute-force attacks**. In fact,
a more common attack is a **dictionary attack**. It is based on trying all the
strings from a predefined list. Usually this would be words from a dictionary.
The attacker also tries different combinations of these strings and makes well-known
substitutes like writing "$" instead of "s" in the words ("pa$$word").

Modern systems almost never store passwords as plain text; they store a **hash**
of a password instead. The hash is a result of applying a one-way function to a password.
The one-way function is a function which is easy to compute on every input, but
hard to invert given the result. A simple example of a one-way function is a product
of two prime numbers. It is easy to multiply two large prime numbers, but very
difficult to find prime factors having only the product.

Hashing Algorithm
plain text - hash functional - hashed text

One of the most used and well-known hashing algorithm families is a SHA (Secure
Hash Algorithm). It uses a number of logical operations (AND, XOR, OR, and others)
on the input to produce its output. SHA usually has a number after its name to
indicate the variant being used. For example, SHA-256 means that the result is
a 256-bit hash. A hash is essentially a fixed-size image of an input string which
can be of any length. An important property of hash functions is that it should
be virtually impossible to find two input strings which would produce the same
hash, but this is still possible because it maps a larger set to a smaller one.
Older versions of hashing algorithms (SHA-1 and MD5) are no longer widely used
because such collisions were found.

## Secure Communications

The two primary methods for encryption used in computer systems:

- Symmetric

  In symmetric encryption, the same key is used for encryption and decryption.
  The key should be somehow passed to both parties beforehand via a secure method.
  If an attacker eavesdrops on the message, he would not be able to understand
  it without the key. One of the simplest symmetric encryptions is **XOR** cipher.
  XOR operation is applied to the message and the key, repeating the key if the
  message is longer than the key. The party receiving the message uses the same
  operation to decrypt the message.

M – message,K – key, E – encrypted message

The encrypted message is E = M XOR K.

- Asymmetric

  In asymmetric encryption (also known as public-key), there are two keys:
  public and private. Each party generates its own pair of keys. A public key
  is used for data encryption and it is shared to everyone. Anyone who wants
  to send an encrypted message to the owner of a pair of keys uses the recipient’s
  public key to encrypt the message. A private key is used for data decryption
  and is kept secret. The combination of a public and a private key is called
  a key pair. The public and private key are mathematically related in such a
  way that even if one knows the public key, it is almost impossible to discover
  the private key. Even if the attacker intercepts the message, it is impossible
  to decrypt it using the public key only.
  One of the most popular public key cryptosystems is RSA, named after its authors,
  Ron Rivest, Adi Shamir, and Leonard Adleman. Without going into much detail,
  it is based on a fact that it is hard to factor the product of two large prime
  numbers. A part of a public key is a number which is a product of two prime numbers.
  The prime factors are never shared to the public, and one of them is a part
  of a private key. One of the disadvantages of asymmetric encryption is that
  generating keys and encrypting messages is much slower compared to symmetric
  encryption. In practice, asymmetric encryption is often used only to establish
  the connection between two parties and obtain a common key for symmetric encryption.

## TLS

TLS (Transport Layer Security) is a cryptographic protocol designed to provide
secure communications over a computer network. Its predecessor is SSL (Secure
Sockets Layer). It utilizes both symmetric and asymmetric encryption.

In the TCP model, the TLS is between the Transport and the Application layers.
It does not exactly fit into any single layer. However, applications generally
use TLS as if it is a transport layer.

The main three functions of TLS are:

- Encryption - to establish a secure channel, both parties should agree on the
  encryption method. TLS uses asymmetric encryption to obtain a common encryption
  key for symmetric encryption.

- Authentication - on the handshake stage, both parties may check the identity
  of each other.

- Integrity - each message includes MAC (Message Authentication Code). This is
  a result of a one-way hash function. The parameters of this function are known
  only to communicating parties.
