# Verify the Sia release signature

All Sia release binaries are signed, which allows you to confirm that the version you've downloaded is indeed the exact version that we've released. This is an extra security check to ensure you're using legit, unmodified software, which can be pretty important when the app also handles money like Siacoins.

{% hint style="info" %}
These instructions are valid for Sia v1.5.0 Equinox. We'll update this as new versions come out, but you can always find the most up-to-date instructions on the Sia [Get Started](https://sia.tech/get-started) page, just under the download links.
{% endhint %}

You can download the signing key [here](https://sia.tech/releases/sia-signing-key.asc), and the signed hashes for the current release [here](https://sia.tech/releases/Sia-v1.5.0-SHA256SUMS.txt.asc).

1. Download and import the Sia signing key. `wget -c https://sia.tech/releases/sia-signing-key.asc` `gpg --import sia-signing-key.asc`
2. Download the signed hash file, and verify the signature. `wget -c https://sia.tech/releases/Sia-v1.5.0-SHA256SUMS.txt.asc` `gpg --verify Sia-v1.5.0-SHA256SUMS.txt.asc`
3. If you downloaded a zip file, unzip that first. `unzip Sia-v1.5.0-linux-amd64.zip`
4. Check that the files you downloaded were signed. `sha256sum --check --ignore-missing Sia-v1.5.0-SHA256SUMS.txt.asc`

You should see "OK" next to the files you did download and errors for the files you have not downloaded.

