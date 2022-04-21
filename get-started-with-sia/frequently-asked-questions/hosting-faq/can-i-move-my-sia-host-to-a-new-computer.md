# Can I move my Sia host to a new computer?

{% hint style="warning" %}
Moving your host isn't recommended. It's a tough process and doesn't have a 100% success rate. Doing so might break your host completely.
{% endhint %}

Both the installation folder and the Sia-UI folders are required to be transferred, on top of preserving the recovery seed.

### Installation locations

| Operating System | Data Directory                              |
| ---------------- | ------------------------------------------- |
| Linux            | `$HOME/.config/Sia-UI`                      |
| Windows          | `Users\\appdata\roaming\Sia-UI\`            |
| macOS            | `$HOME/Library/Application Support/Sia-UI/` |

1. Install Sia on the new system, and start it once to generate the internal data files. Then close Sia completely (right-click the icon in the system tray and select **Quit**) - you don't need to wait for it to synchronize or set up your wallet.
2. Open Sia's internal data files (**About (i) icon > Open Data Folder**) on the old host, then close Sia completely.
3. Move the host storage folders and their contents from the old host to the new host. Obviously, this must be done such that the new storage locations are equal to or larger in size than the old storage locations in order to fit the data. Additionally, the hosting folders need to be accessible in the new machine in the exact same path. For instance, if the host was hosting files in a folder located on D:/Misc/Sia, the new computer will need to have a drive called “D:” and the hosting files placed exactly in /Misc/Sia. **This last requirement makes it impossible to transfer a host from the OS of one family to an OS of a different family** (for example, from Linux to Windows), as the drive routes are different.
4. Move all of Sia's internal data files from the old host to the new host at the locations found above.
5. In the internal data files on the new host, edit the `host\contractmanager\contractmanager.json` and `host\contractmanager\contractmanager.wal` files using a text editor, look for your old storage folder paths, and change them to your corresponding new storage folder paths.
6. Start Sia on the new host.

Sia may take a while to start while it tries to figure out the changes. It may display a message while it does, or it may just sit. Your wallet and host data should be transferred over, though, and hopefully, everything will be in order once Sia finishes loading and you unlock your wallet.
