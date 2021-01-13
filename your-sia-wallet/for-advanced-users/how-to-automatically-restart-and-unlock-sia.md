# How to automatically restart and unlock Sia

When your Sia wallet is locked, it isn't able to perform common and important tasks. For renters, this might mean new contract formation or renewing your allowance. For hosts, it would mean downtime that affects your host scoring and the collateral you've put into contracts.

You can have your Sia wallet automatically unlock by setting up a few simple steps.

## Set the environment variable

An environment variable is just a piece of information that is specific to your computer. In this case, it's your Sia wallet password, so you'll set an environment variable named `SIA_WALLET_PASSWORD`.

[How do I set an environment variable?](how-to-set-an-environment-variable.md)

Environment variables are accessible by any program on your computer. If you still use your Sia seed to unlock your wallet instead of a custom password, you should change this before entering your Sia seed into the environment variable. Someone with access to your seed can easily steal your Siacoins and access your files. Learn how to set a custom password.

## Set your computer to automatically reboot after a power failure

Everything we do here won't matter much if you physically need to reboot your machine after it loses power. At that point, you could just launch Sia again on your own. This setting will allow your computer to reboot automatically anytime its power is interrupted.

[Windows and Linux](https://www.technewsworld.com/story/78930.html) \(done through your BIOS, complete with instructions for connecting to an APC for smooth power-downs and startups\)

[Mac](https://www.wikihow.com/Make-Your-Mac-Restart-Automatically-After-a-Power-Failure) \(only applicable to certain models\)

## Set your user to automatically login on startup

Your computer needs to automatically log in to your user after it reboots. Follow these steps depending on your OS.

[Windows](https://www.groovypost.com/howto/automatically-sign-in-windows-10/)

[Mac](https://support.apple.com/en-us/HT201476)

[Linux Ubuntu](https://help.ubuntu.com/stable/ubuntu-help/user-autologin.html.en), [other distros](http://www.linfo.org/automatic_login.html)

## Set Sia as a startup item

Now that your computer will automatically login after startup, you need to make sure that Sia will launch on its own after that happens.

[Windows](https://support.microsoft.com/en-us/help/4026268/windows-10-change-startup-apps)

[Mac](https://support.apple.com/kb/PH25590?locale=en_US)

[Linux Ubuntu](https://www.howtoforge.com/tutorial/how-to-use-startup-applications-on-ubuntu/), [other distros](https://www.simplified.guide/linux/automatically-run-program-on-startup)

Once all these steps are set, reboot your computer and verify that your account logs in, Sia starts, and your wallet unlocks automatically.

