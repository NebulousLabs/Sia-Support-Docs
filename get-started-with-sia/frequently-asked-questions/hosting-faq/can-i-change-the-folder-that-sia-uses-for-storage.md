# Can I change the folder that Sia uses for storage?

The easiest way to do so is to add the new storage folder in the Host tab, wait for it to show as part of the "Total Storage", and then remove the old storage folder. Sia should move any stored data from the old folder to the new ones once you remove the old one, but this process might take a while depending on the size of the old folder and Sia will be unresponsive during the move.

It may be easier to resize your old storage folders down incrementally after adding the new folder, which will cause Sia to move data from the old folder to the new folder with each resize. If you do this repeatedly in small pieces (e.g. 50 or 100 GB at a time), Sia is less likely to lock up or crash in the process.
