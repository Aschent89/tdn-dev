# tdn-dev
Surface-level Development Environment for TDN (NWN).

## Setup Steps
- `nasher init --default`
- Setup `nasher.cfg` as needed (You'll need to edit the second 'include' to point to the Code Repo you have locally):

```
[Package]
name = ""
description = ""
url = ""
author = ""

[Sources]
include = "module/**/*.{nss,json}"
include = "H:/_Git/tdn/tdn_nss/src/**/*.{nss, json}"

[Rules]
"*.nss" = ".ignore/"
"*" = "module/core/$ext"

# Primary target.  To use this, `nasher pack --yes` is all you need
# on the command line.
[Target]
name = "tdn_development"
file = "tdn_development.mod"
description = ""

# If you want to exclude any files, do so here.  Currently, only
# .nss and .json (gff-converted) resources are included in the
# module build, so you don't need to worry about excluding other
# types of random files.
exclude = "src/nwscript.nss"
exclude = "src/NSSnippets.exe"
exclude = "nwscript.nss"
exclude = "NSSnippets.exe"
```