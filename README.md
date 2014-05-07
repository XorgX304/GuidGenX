GuidGenX
========

GUID generation tool

This is a simple tool to generate GUIDs for applications and services.
It will output GUIDs in the "registry" format:
{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}

Currently supported are the "modern" generation algorithm 4 (random/pseudo-random GUID) and
an ID-linked generation algorithm 4 (which I dubbed v4bis).

About V4bis:
This takes an inputted string of arbitrary length, creates an MD5 hash out of it, XOR-folds
it once to reduce the length to 16 nibbles, and (after setting the required v4 bits) uses
this hash as the "node" part of the GUID, allowing a static part (s) and a dynamic part (x)
of the GUID, for vendor-linked GUIDs:
{xxxxxxxx-xxxx-4xxx-ssss-ssssssssssss}
