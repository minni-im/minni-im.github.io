---
layout: post
title: Deal with it stupid cache
categories: code
---

Cache issue should be over now, as I implemented the mecanism I was describing in my [previous post][stupid_cache].

All javascript files are now packaged (ie regrouping several files into a single one) with a hash in the filename to make them unique
(I basically append to the filename a [md5 hash][md5] based on the file content).

With that in place, any single change in any file will generate a new file! _Deal with it stupid cache_!

[stupid_cache]: http://blog.roulotte.im/2013/01/stupid-cache/
[md5]: http://en.wikipedia.org/wiki/MD5