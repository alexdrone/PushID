# PushID
[![Swift](https://img.shields.io/badge/swift-3.1-orange.svg?style=flat)](#)
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)](https://opensource.org/licenses/MIT)


Robust and thread-safe generator for UUIDs with guaranteed chronological ordering based on [Firebase's PushID](https://firebase.googleblog.com/2015/02/the-2120-ways-to-ensure-unique_68.html).

ID generator that creates 20-character string identifiers with the following properties:
  1. They're based on timestamp so that they sort *after* any existing ids.
  2. They contain 72-bits of random data after the timestamp so that IDs won't collide with other clients' IDs.
  3. They sort *lexicographically* (so the timestamp is converted to characters that will sort properly).
  4. They're monotonically increasing. Even if you generate more than one in the same timestamp, the latter ones will sort after the former ones.  We do this by using the previous random bits but "incrementing" them by 1 (only in the case of a timestamp collision).
  
 
 ### Usage
 
``` swift
let id = makePushID() //-Kk6Xfa37VrgLYFtTygJ
```

### Credit

Original javascript implementation [here](https://gist.github.com/mikelehen/3596a30bd69384624c11).

### Other languages

[C](https://gist.github.com/whatvn/15f5266d59320113d978)
[Java](https://gist.github.com/swftvsn/438b4ed68619ad1f5d1c251dc3a5af6f)
[Go](https://github.com/kjk/betterguid)
[C#](https://gist.github.com/kiliman/ca1d9f4135078a6b24c5005113bbeea4)
[Obj-C](https://gist.github.com/kcmoffat/af856ab4b605a00216d3b5f627e50a84)
[Typescript](https://gist.github.com/episage/0fa8fcf71a28985197c9ba1d51f84408)
[Ruby](https://gist.github.com/azell/b96d27e4091f5a966bae)
[Python](https://gist.github.com/risent/4cab3878d995bec7d1c2)
[Elm](https://github.com/ryanucode/firebase-effect-manager)
[SQL](https://gist.github.com/DimuDesigns/2fd0adf5b56a5ebf7cc27f64bff13fd2)
[Lua](https://github.com/tst2005/lua-firebase_pushid/blob/master/firebase_pushid.lua)


