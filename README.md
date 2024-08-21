# Alibi

## High-resolution location proofs with TLSNotary

This is a project submitted for the [Web3 Summit](https://web3summit.com/) 2024 hackathon.

### Pitch

Proof of geolocation over time has many use-cases, but it must have acceptable privacy and be VIP (Verifiable, Interoperable, Portable); by leveraging internet security and vast personal data tracked by Google, we can extract data privately and prove its origin publicly.

Alibi enables anyone with a Google account to prove their historical location without sharing more information than necessary; this creates a proof that can be used in any context, thus bringing web2 data into a form suitable for web3.

Though what we have is a proof of concept, we want to produce meaningful facts about geolocation over time without leaking additional data: “I spent over 180 days in Berlin in 2021”, “I wasn’t at the scene of the crime”, “I have been to this restaurant over 20 times, where is my free kimchi” – and then make it portable enough for onchain verifiers.  

### Source

The [alibi-client](https://github.com/w3s-alibi/alibi-client) repo contains a React app that handles onboarding and a proof viewer.

The [tlsn-plugin](https://github.com/w3s-alibi/tlsn-plugin) repo contains a TLSNotary extension plugin.

### Running the stack

* Instructions to run TLSNotary are [available here](https://docs.tlsnotary.org/quick_start/browser_extension.html).
* Once the server and proxy are running, and the extension is installed, the extension options must be set to use the local server/proxy.
* The app can simply be run with `bun dev`.

### How it works

* Users must first install the TLSNotary extension. This should be built from source from [our fork](https://github.com/w3s-alibi/tlsn-extension).
* When the extension is open, users should install the plugin. This is available to download from our app.
* Users can then open the plugin. It should take them to timeline.google.com where they can log in if needed.
* The user can select a day and then run the third step of the plugin, to notarise the data.
* A proof will then be generated, which can be downloaded or copied to clipboard.
* The app offers a proof viewer; just paste the `recv` text from the extension, and you can see a map with the user's email address, location path and timestamps.

### License: WTFPL
