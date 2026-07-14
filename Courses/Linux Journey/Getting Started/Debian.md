Debian has existed since the early days of Linux and has built a reputation for careful engineering, opennes and long-term reliability.

![[Pasted image 20260714104156.png]]

Debian is also widely known in its role in the large Linux ecosystem. It has served the foundation for many other distributions. 

A main feature of debian is its branch model:
- Stable : The official release. It priorities reliability and security over having
- Testing : Contains packages that are being prepared for the next stable release. 
- Unstable : Known as "Sid". Where active development happens. New packages enter here first.

Testing and Unstable are rolling branches because package updates flow into them continuously instead of waiting for a single finished Stable release.

Debian follows a release based model. Debian does not chase rapid change. Major updates usually appear in testing or unstable  before becoming part of the next Stable release.
# Package Management
Debian uses the `.deb` package format and the `APT` toolset to install, update, remove and manage software. 

To install `.deb` files run this command
```bash
sudo install ./your_file.den
```