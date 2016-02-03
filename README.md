# Proxifier Profiles
A ruleset for Proxifier on OS X, which is useful in China Mainland, especially when your network is unstable.

## Features
Rules:

- Direct connection:
    - Other common proxy softwares (to prevent infinite loop)
    - Localhost
    - Link-local addresses and LANs (with IPv6 considered)
    - Common router management addresses (IPs and fake domains)
    - Chinese sites, via:
        - Common CDNs
        - Multimedia content providers
        - Domain whitelist
        - IP ranges
    - Other common district-restricted contents (Steam, etc.)
- Forced proxy:
    - Blocked services
        - Google, Dropbox, Gravatar, Wordpress, etc.
        - Support all Google desktop softwares
        - include those embedded in OS X system preferences
    - Unstable services
        - iTunes / App Store / iCloud
          (Plus, if your proxy have a data limit, you can filter out App Store downloads individually.)
        - Microsoft services
        - Services for programmers: Github, Homebrew, PyPI, Atom, Android SDK, etc.
        - Games: Minecraft, etc.
        - Common foreign CDNs

These rules are split into individual items so you can simply enable or disable one using Proxifier's built-in mechanism, or redirect any of them to another proxy.

## Notes
- `Profiles/Current.ppx` is what I use daily. Others are for debugging so you can safely delete them.
- Default proxy is a local SOCKS5 proxy listening on port 1080.
- These rules are designed to be as narrow as possible to minimize their side effects or unwanted data via proxy, and achieve maximize speed. If your local ISP is no more reliable than your proxy provider, modify rule "Default" (which is at the bottom) to use proxy.
- This is not a replacement of system-level proxy settings. Generally speaking, any application which correctly applies system-level proxy (whether PAC or SOCKS5) are not considered to be included in this ruleset.
- Some applications, such as "Atom Helper", may leads to false infinite loop alerts -- It's safe to ignore them most of the time.
- Proxifier can't handle UDP connections so if you are a game player you may need ProxyCap; however, ProxyCap's design is not suitable for this purpose, so I prefer sticking with Proxifier.
- Proxifier is an (somewhat expensive) commercial software. The use of pirated software is not encouraged. Come on and be an adult.

Feel free to contact me if you think there are something missing or some software behaves incorrectly.


## License

This "thing" is released under ISC License.

```
Copyright (c) 2016, James Swineson <jamesswineson@gmail.com>

Permission to use, copy, modify, and distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```

## References
- See [Jamesits/chnroutes](https://github.com/Jamesits/chnroutes/tree/feature/proxifier) for Chinese IP ranges support.
