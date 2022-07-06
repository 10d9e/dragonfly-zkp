# dragonfly-zkp
Dragonfly zero-knowledge proof method, used in WPA-3 for Simultaneous Authentication of Equals (SAE)

# Implementation

WPA3, also known as Wi-Fi Protected Access 3, is the third iteration of a security certification program developed by the Wi-Fi Alliance. WPA3 is the latest, updated implementation of WPA2, which has been in use since 2004. The Wi-Fi Alliance began to certify WPA3-approved products in 2018.

The WPA3 protocol provides new features for personal and enterprise use such as 256-bit Galois/Counter Mode Protocol (GCMP-256), 384-bit Hashed Message Authentication Mode (HMAC) and 256-bit Broadcast/Multicast Integrity Protocol (BIP-GMAC-256). The WPA3 protocol also supports security measures such as perfect forward secrecy.

With WPA-2 (802.11i) seen as flawed, the Wi-Fi Alliance has released WPA-3, and which introduces almost seamless protection against brute-force attacks for network passwords. The protection only allows for one change to crack a password. As with WPA-2, it is available in two forms:

WPA3-Personal: This replaces the 4-way handshake with Simultaneous Authentication of Equals (SAE) [1] and which is defined in the IEEE 802.11s standard. SAE was initially defined for mesh networks, but is now scaling to infrastructure wireless networks.
WPA3-Enterprise: This integrates a back-end authentication infrastructure, such as with a RADIUS server. Elliptic Curve Diffie-Hellman (ECDH) exchange and Elliptic Curve Digital Signature Algorithm (ECDSA) using a 384-bit elliptic curve are used to a strong authentication.
Along with these changes, WPA-3 brings the integration of QR codes to gain the network connection details.

The focus for Simultaneous Authentication of Equals (SAE) is to properly authenticate a device onto a network and using a password and MAC addresses to authenticate. An intruder should not be able to connect to a network unless they known password that the access point uses. Also, an intruder should not be able to guess either the password or the long-term authentication element of the password. In WPA-2 an intruder can listen to the 4-way handshake and can then brute force the password from hashed value created (see the section below for details).

With SAE which is based on a zero-knowledge proof known as dragonfly we use the Diffie-Hellman key exchange method but adds an authentication element. With this we create a shared key with elliptic curve methods (NIST curves), and then use a pre-shared key and MAC addresses. When the client connects to the access point, they perform an SAE exchange. If successful, they will each create a cryptographically strong key, of which the session key will be derived from. If one session key is cracked it will only affect one key, and not all of the key used, as with WPA-2.

# Citations

Buchanan, William J (2022). Dragon Fly - Zero Knowledge Proof with ECC. Asecuritysite.com. https://asecuritysite.com/zero/dragonfly2

TechTarget Contributor(2022). WPA3. TechTarget.com. https://www.techtarget.com/searchsecurity/definition/WPA3
