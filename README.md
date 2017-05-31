# LabView wrapper VIs for Mirao 52e API
This is a LabView wrapper code for deformable mirror [Mirao 52e](http://www.imagine-optic.com/en/product/mirao-52-e/0/0/) API 
that comes with the mirror as a DLL file.
The actual DLL file is *not* provided, respecting the IP of the manufacturer. 

The LabView VIs were generated using **Import Shared Library Wizard** as described in this 
[tutorial](https://forums.ni.com/t5/Developer-Center-Resources/Tutorial-Creating-Wrapper-VIs-for-C-C-DLL-functions-using-the/ta-p/3522566), 
and then edited and tested manually using a Mirao mirror.

To install make sure each VI knows where to find the Mirao DLL file on your computer. To do this, go to wire diagram of the VI, double-click the `Call Library Function Node` and set your path to `mirao52e.dll` file:
![setting dll path](/screenshots/call_library_path.png "setting mirao52e.dll path")

# Screenshots
![library tree](/screenshots/library_tree.png "mirao52e_32bit.lvlib tree")
![mro_open](/screenshots/mro_open.png "Wrapper for mro_open(int *status)")
![mro_open](/screenshots/mro_open_wire.png "Wire diagram mro_open(int *status)")
![mro_setMonitoringEnabled](/screenshots/mro_setMonitoringEnabled.png "Wrapper for mro_setMonitoringEnabled (MroBoolean enabled, int *status)")
![mro_applyCommand](/screenshots/mro_applyCommand.png "Wrapper for mro_applyCommand (MroCommand command, MroBoolean trig, int *status)")

Most of the API functions (18) are ported and tested in LabView, except 6 functions for stock command operations, marked `incomplete`. Those may be added later.

DLL file version used: x86 (32-bit)

Mirao 52e API version: 001.001.20131209.

LabView version: 2016, 32 bit.
