# Key Transition Statement

Date: 2021/07/01

I have recently set up a new OpenPGP key,
and will be transitioning away from my old one.

The old key will continue to be valid for some time, but I prefer all
future correspondence to come to the new one. I would also like this
new key to be re-integrated into the web of trust.  This message is
signed by both keys to certify the transition.

The old key was:

```
pub   ed25519/7871C05E7D8EC204 2019-12-06
Key fingerprint = 48DD28C2039E3CE2632C6CCA7871C05E7D8EC204
```

And the new key is:

```
pub   nistp521/128866201FD50FEE 2021-07-01 [expires: never]
Key fingerprint = 1F3735FF4190675B1088A69A128866201FD50FEE
```

To fetch the full key from a public key server, you can simply do:

```
gpg --keyserver keys.openpgp.org --recv-key '1F3735FF4190675B1088A69A128866201FD50FEE'
```

If you already know my old key, you can now verify that the new key is
signed by the old one:

```
gpg --check-sigs '1F3735FF4190675B1088A69A128866201FD50FEE'
```

If you don't already know my old key, or you just want to be double
extra paranoid, you can check the fingerprint against the one above:

```
gpg --fingerprint '1F3735FF4190675B1088A69A128866201FD50FEE'
```

If you are satisfied that you've got the right key, and the UIDs match
what you expect, I'd appreciate it if you would sign my key. You can
do that by issuing the following command:

**
NOTE: if you have previously signed my key but did a local-only
signature (lsign), you will not want to issue the following, instead
you will want to use --lsign-key, and not send the signatures to the
keyserver
**

```
gpg --sign-key '1F3735FF4190675B1088A69A128866201FD50FEE'
```

I'd like to receive your signatures on my key. You can either send me
an e-mail with the new signatures (if you have a functional MTA on
your system):

```
gpg --export '1F3735FF4190675B1088A69A128866201FD50FEE' | gpg --encrypt -r '1F3735FF4190675B1088A69A128866201FD50FEE' --armor | mail -s 'OpenPGP Signatures' <alt@sfc.wide.ad.jp>
```

Please let me know if you have any questions, or problems, and sorry
for the inconvenience.

Wataru Ohgai

*This document is based on [this](https://help.riseup.net/en/security/message-security/openpgp/key-transition)
