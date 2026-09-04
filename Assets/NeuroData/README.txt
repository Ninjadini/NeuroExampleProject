Neuro data normally lives outside Assets, at the project root, where Unity never imports it.
It sits inside Assets here only so the demo can ship as a .unitypackage, which cannot contain
anything outside Assets/ - the cost is a .meta file for every .json.
This folder is registered as an ExtraDataPath. The Primary Data Path is still the default
"NeuroData" at the project root, so new Neuro ref files are created there, not here.
