# Decentralized Information Distributor (DID)

DID is a novel decentralized social media infrastructure that empowers users to own and distribute their content. Think of it like a decentralized Twitter where the data is entirely in the user's hands and where everyone is free to post content and subscribe to new posts.

⭐ Don't like to read? Feel the power of DID [by publishing your first social post](https://writer.did-1.com/)

## Table of Contents

- [Architecture](#architecture)
- [Repositories](#repositories)
  - [demo-writer](#demo-writer)
  - [instance-nodejs](#instance-nodejs)
  - [demo-reader](#demo-reader)
- [How it Works](#how-it-works)
- [Motivation](#motivation)
- [Contribute](#contribute)
- [License](#license)

## Architecture

DID consists of three integral repositories:

1. **demo-writer:** A user-friendly onboarding tutorial to generate keys and social posts.
2. **instance-nodejs:** The heart of the DID network. It validates, stores, and distributes the post information.
3. **demo-reader:** A platform that displays the information from the DID network in a user-friendly format.

## Repositories

### demo-writer

This tutorial helps new users get started with DID:

- Generate private/public key pairs using the secp256k1 algorithm.
- Craft DID-compliant HTML documents for social posts.
- Guide on uploading the public key and post to their personal domain.
- Submit the post URL to the DID instance for publishing.

### instance-nodejs

[Go to repository](https://github.com/did-1/did-instance-nodejs)

The core of the DID p2p network:

- Receives URL submissions and validates them.
- DOES NOT save post content, only URLs, signatures, domains, and content hashes.
- Distributes validated information to other peers on the network.

### demo-reader

A platform to consume DID content:

- Crawls URLs from DID instance databases.
- Stores post data locally.
- Displays data in a Twitter-like interface, showing domains and "retweet" equivalents.

## How it Works

1. **Key Generation:** User creates a private/public key pair (secp256k1).
2. **Key Hosting:** User hosts the private key on their domain (e.g., `userdomain.com/did.pem`).
3. **Content Creation:** User crafts a DID-compliant HTML page with their post and hosts it on their domain.
4. **Submission:** User signs the hash of their content and URL and sends this to a DID instance.
5. **Validation:** DID instance verifies the post's signature, content, and other aspects, then saves the URL and signature.
6. **Propagation:** The URL's information is broadcasted on the p2p network for other instances to validate and store.
