# Find or fix your seed

Your seed is the most imortant part of your Sia node because it controls access to your wallet and files. You need to keep it safe, but there are a few tools you have available to find or fix your Sia seed.

These commands can be used directly in `siac`. In Sia-UI, open the Terminal from the toolbar on the top of the app.

## If Sia is already unlocked

You might use a custom password to access Sia. If you do, you don't often type your seed in and you may need a refresher on what it is.

Unlock your wallet and open the Terminal. Type `wallet seeds`.

Your seed will be displayed. [Make sure you store your seed safely.](../the-importance-of-your-seed.md)

## Use siac utils

siac utils has a couple commands that can help you troubleshoot your seed.

### verify-seed

This will attempt to diagnose an issue with your seed.

**Usage** `./siac utils verify-seed`

You'll be asked to provide your seed, at which point Sia will provide one of the following outputs:

#### Success

* No issues detected with your seed - _the seed you provided meets all the requirements for a Sia seed, and should be valid_

#### Failure

* invalid formatting - _usually indicative of extra spaces in between words or at the end, or no spaces between words_
* seed is not valid: must be 28 or 29 words - _your seed is too short or too long_
* seed is not valid: all words must be lowercase - _there is a capital letter somewhere in your seed_
* seed is not valid: illegal character - _you have something other than a letter in your seed_

### bruteforce-seed

If your seed is missing one word, this will attempt to figure out the missing word. This can also be used to check a word you're not sure about, by deleting it and then running this.

**Usage** `./siac utils bruteforce-seed`

You'll be asked to provide your partial seed, and Sia will get to work. It may take a couple of minutes to complete. Sia will provide one of the following outputs:

#### Success

* Found valid seed! The missing word was &lt;word&gt;.

Sia will then print the entire correct seed for you to store safely.

#### Failure

* No valid seed - _the utility was unable to find your missing word_
* Expected 27 or 28 words in partial seed, got &lt;n&gt; - _the partial seed you provided was missing more than one word_
* Couldn't read seed - _the partial seed you provided was invalid in other ways_

