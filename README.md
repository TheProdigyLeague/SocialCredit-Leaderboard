<img src="https://tse4.mm.bing.net/th?id=OIP.QbybAsrZ3i6788AslQ4vtQHaE8&amp;pid=Api" alt="Network Sockets: The Bridges Between End Systems - αlphαrithms"/>

# 統合開発環境

[![Windows, Ubuntu](https://github.com/ValveSoftware/GameNetworkingSockets/actions/workflows/build.yml/badge.svg)](https://github.com/ValveSoftware/GameNetworkingSockets/actions)  [![MacOS](https://github.com/ValveSoftware/GameNetworkingSockets/actions/workflows/macos.yml/badge.svg)](https://github.com/ValveSoftware/GameNetworkingSockets/actions) [![Linux flavors](https://github.com/ValveSoftware/GameNetworkingSockets/actions/workflows/linux-flavors.yml/badge.svg)](https://github.com/ValveSoftware/GameNetworkingSockets/actions)

# What is Gaming Sockets?

Gaming Sockets are basic transport layers for games.  The features are:

* Connection-oriented API (like TCP, but UDP is not stream-oriented).
* Basically, if you have an underlying machine transporting unreliable protocols. Steam will perform the fragmentation, reassembly, and retransmission for the End-User messages.

> Sophisticated TCP window vector models from DCCP-RFC 4340 in section 11.4 Google QUIC within the context of stylized SNP WIRE formatting in the clients library that reliably ordered messaging systems must utilize receiver packes effeciently to communicate via sender numbers. Informing the packets segemented into each deductive layer that retransmits crypto. ~Glenn Fiedler

> AES-GCM-256 per packet. ~Curve25519

For the key exchange to certify host signatures. The shared key derivations must follow per-packet IV algorithms based on Google QUIC protocols.

1. [TedTalks](https://cr.yp.to/ecdh.html)

```JavaScript
\n
\u0012\u001c
AEAD\n
\u001c Authenticated encryption: the tag of the AEAD algorithm to be used.\n
\u0012\u001cKEXS\n
\u001c Key exchange: the tag of the key exchange algorithm to be used.\n
\u0012\u001cNONC\n
\u001c Client nonce: 32 bytes consisting of 4 bytes of timestamp (big-endian, UNIX epoch seconds), 8 bytes of server orbit and 20 bytes of random data.\n
\u0012\u001cSNO\n
\u001c Server nonce (optional): an echoed server nonce, if the server has provided one.\n
\u0012\u001cPUBS\n
\u001c Public value: the client’s public value for the given key exchange algorithm.\n
\u0012\u001cCETV\n
\u001c Client encrypted tag-values (optional): a serialised message, encrypted with the AEAD algorithm specified in this client hello and with keys derived in the manner specified in the CETV section, below. This message will contain further, encrypted tag-value pairs that specify client certificates, ChannelIDs etc.\n
\u0011\n
After sending a full client hello, the client is in possession of non-forward-secure keys for the connection since it can calculate the shared value from the server config and the public value in PUBS. (For details of the key derivation, see below.) These keys are called the initial keys (as opposed the the forward-secure keys that come later) and the client should encrypt future packets with these keys. It should also configure the packet processing to accept packets encrypted with these keys in a latching fashion: once an encrypted packet has been received, no further unencrypted packets should be accepted.\n"}

```

![valvesoftware](https://github.com/user-attachments/assets/b05b68f8-d99e-42c8-997d-7e4dc48aa8d9)

## Does Valve have a tool for simulated packets?

Steam is a tool for monitoring latency/loss. And details the statistics in a measured environment. User's bandwidth and head-of-line blocking control mechanisms shares multi-line message streaming lanes on connections. Strictly prioritizing property values. Sorting on a weighted scale for fair match queueing that controls shareable bandwidth and in combination of methodology via IPv6-P2P. Network Acess Tunnels traverse through Google's QUIC WebRTC ICE algorithm implementations via pluggable IDE signal services utilizing symmretric connectivity modes via Universal Identifiers. Steam's network specifically includes interfaces designed and tailored to be portable among a robust UDP-P2P environment. In recent case studies:

> UDP-based design is non-connected to oriented timing measurements with each packet specifying recipients adresses accross platforms. Steam libraries must be shopped on consoles, mobile, and even in non-steam stores! Allowing transparent facilitation accross inter-connectivity. 

### Can I get access to the code?

No, this requires a higher level of serialization amongst your ISP entity. Our delta encoding utilizes changed state variables via compression.

#### Quick API overview

SteamAPI is a web-based client offering various forms of exlusitivity, only available to Gabe and Valve Associates. Thus, their features of oauth certs and signaliing services rely on an `SDR_MTU` relay interface. (Software Designed Radio with MultiThreadedUtilization).

## A Very Simple Client/Server/Program

The intended design is for User's (mostly of the middle-upper middle class) to install Steam. Plugin their ethernet cable and play games. However, further and recent testing with case studies show that ordinary IPv4 addresses will suffice. C++ allows hosts to connect using seamless P2P writing service plugins via `.NET, CORS`.

### English as a Second Language

Valve Software and Steam was built with C++. The plain interface and facility is a binding agreement among other languages.

```JavaScript
// nxrighthere

<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto">ConfigurationValue</h4><a id="user-content-configurationvalue" class="anchor" aria-label="Permalink: ConfigurationValue" href="#configurationvalue"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto">Definitions of configuration values:</p>
<p dir="auto"><code>ConfigurationValue.Invalid</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketLossSend</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketLossRecv</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketLagSend</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketLagRecv</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketReorderSend</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketReorderRecv</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketReorderTime</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketDupSend</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketDupRecv</code></p>
<p dir="auto"><code>ConfigurationValue.FakePacketDupTimeMax</code></p>
<p dir="auto"><code>ConfigurationValue.TimeoutInitial</code></p>
<p dir="auto"><code>ConfigurationValue.TimeoutConnected</code></p>
<p dir="auto"><code>ConfigurationValue.SendBufferSize</code></p>
<p dir="auto"><code>ConfigurationValue.SendRateMin</code></p>
<p dir="auto"><code>ConfigurationValue.SendRateMax</code></p>
<p dir="auto"><code>ConfigurationValue.NagleTime</code></p>
<p dir="auto"><code>ConfigurationValue.IPAllowWithoutAuth</code></p>
<p dir="auto"><code>ConfigurationValue.MTUPacketSize</code></p>
<p dir="auto"><code>ConfigurationValue.MTUDataSize</code></p>
<p dir="auto"><code>ConfigurationValue.Unencrypted</code></p>
<p dir="auto"><code>ConfigurationValue.EnumerateDevVars</code></p>
<p dir="auto"><code>ConfigurationValue.SymmetricConnect</code></p>
<p dir="auto"><code>ConfigurationValue.LocalVirtualPort</code></p>
<p dir="auto"><code>ConfigurationValue.ConnectionStatusChanged</code></p>
<p dir="auto"><code>ConfigurationValue.AuthStatusChanged</code></p>
<p dir="auto"><code>ConfigurationValue.RelayNetworkStatusChanged</code></p>
<p dir="auto"><code>ConfigurationValue.MessagesSessionRequest</code></p>
<p dir="auto"><code>ConfigurationValue.MessagesSessionFailed</code></p>
<p dir="auto"><code>ConfigurationValue.P2PSTUNServerList</code></p>
<p dir="auto"><code>ConfigurationValue.P2PTransportICEEnable</code></p>
<p dir="auto"><code>ConfigurationValue.P2PTransportICEPenalty</code></p>
<p dir="auto"><code>ConfigurationValue.P2PTransportSDRPenalty</code></p>
<p dir="auto"><code>ConfigurationValue.SDRClientConsecutitivePingTimeoutsFailInitial</code></p>
<p dir="auto"><code>ConfigurationValue.SDRClientConsecutitivePingTimeoutsFail</code></p>
<p dir="auto"><code>ConfigurationValue.SDRClientMinPingsBeforePingAccurate</code></p>
<p dir="auto"><code>ConfigurationValue.SDRClientSingleSocket</code></p>
<p dir="auto"><code>ConfigurationValue.SDRClientForceRelayCluster</code></p>
<p dir="auto"><code>ConfigurationValue.SDRClientDebugTicketAddress</code></p>
<p dir="auto"><code>ConfigurationValue.SDRClientForceProxyAddr</code></p>
<p dir="auto"><code>ConfigurationValue.SDRClientFakeClusterPing</code></p>
<p dir="auto"><code>ConfigurationValue.LogLevelAckRTT</code></p>
<p dir="auto"><code>ConfigurationValue.LogLevelPacketDecode</code></p>
<p dir="auto"><code>ConfigurationValue.LogLevelMessage</code></p>
<p dir="auto"><code>ConfigurationValue.LogLevelPacketGaps</code></p>
<p dir="auto"><code>ConfigurationValue.LogLevelP2PRendezvous</code></p>
<p dir="auto"><code>ConfigurationValue.LogLevelSDRRelayPings</code></p>
```

<hr>

```JavaScript
// facepunch

Console.WriteLine( $&quot;Title: {itemInfo?.Title}&quot; );
    Console.WriteLine( $&quot;IsInstalled: {itemInfo?.IsInstalled}&quot; );
    Console.WriteLine( $&quot;IsDownloading: {itemInfo?.IsDownloading}&quot; );
    Console.WriteLine( $&quot;IsDownloadPending: {itemInfo?.IsDownloadPending}&quot; );
    Console.WriteLine( $&quot;IsSubscribed: {itemInfo?.IsSubscribed}&quot; );
    Console.WriteLine( $&quot;NeedsUpdate: {itemInfo?.NeedsUpdate}&quot; );
    Console.WriteLine( $&quot;Description: {itemInfo?.Description}&quot; );"><pre>
<span class="pl-smi">var</span>
<span class="pl-s1">itemInfo</span> <span class="pl-c1">=</span>
<span class="pl-k">await</span> Ugc<span class="pl-kos">.</span>Item<span class="pl-kos">.</span>
<span class="pl-en">Get</span><span class="pl-kos">(</span> <span class="pl-c1">1720164672</span>
<span class="pl-kos">)</span><span class="pl-kos">;</span>
```

<hr>

```JavaScript
// nielsad

<ul dir="auto">
<li>Connection-oriented API (like TCP)</li>
<li>... but message-oriented (like UDP), not stream-oriented.</li>
<li>Supports both reliable and unreliable message types</li>
<li>Messages can be larger than underlying MTU.  The protocol performs
fragmentation, reassembly, and retransmission for reliable messages.</li>
<li>Encryption. AES-GCM-256 per packet, <a href="https://cr.yp.to/ecdh.html" rel="nofollow">Curve25519</a> for
key exchange and cert signatures. The details for shared key derivation and
per-packet IV are based on the <a href="https://docs.google.com/document/d/1g5nIXAIkN_Y-7XJW5K45IblHd_L2f5LTaDUDwvZ5L6g/edit?usp=sharing" rel="nofollow">design</a>
used by Google's QUIC protocol.</li>
<li>Tools for simulating loss and detailed stats measurement.</li>
<li>IPv4 + IPv6</li>
</ul>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto">gns features</h3><a id="user-content-gns-features" class="anchor" aria-label="Permalink: gns features" href="#gns-features"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ul dir="auto">
<li>Support for dynamic/static linking</li>
<li>API documentation available via <code>godoc</code></li>
<li>Compatible with <a href="https://golang.org/pkg/net/#Conn" rel="nofollow">net.Conn</a> and <a href="https://golang.org/pkg/net/#Listener" rel="nofollow">net.Listener</a></li>
</ul>
```

## Why do I see "Steam" everywhere?

Our marketing teams, mostly. Steam has been around since the early 2000's. But, with the advent of digital currencies and key exchanges. Everyone and their mother has at least heard of Steam. It's extremely popular. And Gabe has kept his boot on the neck of competitors for over a decade now. If you didn't have a PC with steam back then, you were exiled. And if you don't have a high level Steam account now, you are also exiled. Steam is incorporated into our database as well with names like `SteamNetworking` and `SteamSocks`. Many files downloaded with Steam are compressed in the tar bals. And have been retro-fitted for the games that are available among the Steam networking infrastructure. 

Many of Gabe's partners have subset functionalities of ValveSoftware's API. Such as:

```JavaScript
// SteamWorks SDK
/// Connection handle
        HSteamNetConnection m_hConn;

        /// Full connection info
        SteamNetConnectionInfo_t m_info;

        /// Previous state.  (Current state is in m_info.m_eState)
        ESteamNetworkingConnectionState m_eOldState;
};
</div><h2 class="bb_subsection"><a name="SteamNetAuthenticationStatus_t"></a>SteamNetAuthenticationStatus_t</h2><br>A struct used to describe our readiness to participate in authenticated, encrypted communication.  In order to do this we need:<br><ul class="bb_ul "><li> The list of trusted CA certificates that might be relevant for this app.<br></li><li> A valid certificate issued by a CA.</li></ul><br>This callback is posted whenever the state of our readiness changes.<br><br><div class="bb_code ">struct SteamNetAuthenticationStatus_t
{ 

        /// Status
        ESteamNetworkingAvailability m_eAvail;

        /// Non-localized English language status.  For diagnostic/debugging
        /// purposes only.
        char m_debugMsg[];
};
</div><h2 class="bb_section"><a name="custom_signaling"></a>Custom P2P signaling</h2><i>Signaling</i> refers to rendezvous messages sent through a trusted channel that is low bandwidth and high latency, used by peers to negotiate a P2P connection.  Steam provides a signaling service for you.  However, in some situations you may wish to do your own signaling.  (For example, if one or both of your peers are not on Steam.)  You can use SteamNetworkingSockets to make P2P connections, with your own signaling.  You can use ICE to pierce NAT and use standard STUN/TURN servers, or depending on your situation, SDR relay network and Valve backbone may not be available.  Please let us know if you need more information about these APIs.<br><br></div>    <div id="hashLocationHighlight"></div>
                        </div>
                </div>
        </div>
</div>
<li><em>Documentation</em></li>
                                <li><a href="https://partner.steamgames.com/doc/">Home</a></li>
                                <li><a href="https://partner.steamgames.com/doc/gettingstarted">Getting Started</a></li>
                                <li><a href="https://partner.steamgames.com/doc/store">Store Presence</a></li>
                                <li><a href="https://partner.steamgames.com/doc/features">Features</a></li>
                                <li><a href="https://partner.steamgames.com/doc/finance">Finance</a></li>
                                <li><a href="https://partner.steamgames.com/doc/marketing">Sales & Marketing</a></li>
                                <li><a href="https://partner.steamgames.com/doc/sdk">Steamworks SDK</a></li>
                                <li><a href="https://partner.steamgames.com/pccafe">Café Licensing</a></li>
                                <li><a href="https://partner.steamgames.com/doc/features/steamvr/info">Steam VR</a></li>
                        </ul>
                        <ul>
                                <li><em>Resources</em></li>
                                <li><a href="https://partner.steamgames.com/vrlicensing">Steam VR</a></li>
                                <li><a href="https://partner.steamgames.com/pccafe">Steam PC Café Program</a></li>
                                <li><a href="https://steamcommunity.com/groups/steamworks/discussions">Steamworks Discussions <i class="icoExternal"></i></a></li>
                                                                        <li><a href="https://www.youtube.com/user/SteamworksDev">Steamworks Video Tutorials <i class="icoExternal"></i></a></li>
                                                            <li> <a class="header_login_btn footerbtn" href="https://help.steampowered.com/en/wizard/HelpWithPublishing"><span>Contact Support </span></a></li>
            </ul>
                        <ul>
                                <li><em>News & Updates</em></li>
                                <li><a href="https://store.steampowered.com/news/group/4145017">Steamworks Blog <i class="icoExternal"></i></a></li>
                                <li><a href="https://store.steampowered.com/news/app/593110">Steam Blog <i class="icoExternal"></i></a></li>
                                <li><a href="https://store.steampowered.com/news/app/250820">Steam VR Blog <i class="icoExternal"></i></a></li>
                                <li><a href="https://store.steampowered.com/news/app/1675180">Steam Deck Blog <i class="icoExternal"></i></a></li>
                        </ul>
                </div>
        </div>
</div>
<script type="text/javascript">
        </script>
```

### Steam will remain 'Free & Open-Source'?

![steamASCII](https://github.com/user-attachments/assets/97969e2a-8cc8-4190-8a71-499394a01f3d)

Gabes main reason for this code is that competitors like Discord now are growing without any hesitation. So, releasing an SDK was the best bet to keep up with current market trends. With rapid release cycles and compatibility requirements being on demand and in store shelves, now more than ever are customer's taking advantage of newer, greater, and faster services. Especially with live streaming on the rise and social credit controlling our everyday lives. Gabe needs his security team to port backwards compatibliity and to burden Valve's `MTU_SDR` due to business partnership programs versioning their systems. Game Developers now are still fighting for **_Free & Open Source_**. As the saying goes **Never Again**. The licensing requirements to be authorized nowadays aren't to Gabe's liking. Thus, the maximum advantage would be to release features like Steamworks so that the next time a major exploit is released out into the public domain and bounty hunters catch wind of this 'wart' in the system, Valve needs to keep the current packaging contents, at the very least, `opensource version available #ifdef STEAM`. Competitors will try to out-match Gabe's Steamworks SDK project. But, this explains the behavior of anachronistic coding styles that display wierd directory layouts. Moreover, this will be kept in sync with Valve Software's Steam project. When Gabe extracted competitors code from much larger codebases. He implemented `rel="gross" <hackery>`

```Python
import sys
import os
import pandas
import lambda
import godMode

from { lambda, godMode} export players

players = {
  "◆︎⬧︎♏︎❒︎🕯︎⬧︎ ⬧︎⧫︎♏︎♋︎❍︎": $2y$10,
  "◻︎❒︎□︎♎︎◆︎♍︎⧫︎": $1vi1c,
  "🙵♏︎⍓︎ ⧫︎□︎🙵♏︎■︎": AdyIoT,

} # leaderboard by social credit in automatic order
sorted_players = sorted(players.items(), key=lambda x: x[1], reverse=True)

# leaderboard displayed to public at large

print("Leaderboard:")
for rank, (player, score) in enumerate(sorted_players, 1):
  print(f"{rank}, {player}, {score}")
```

<hr>

```cc
struct addrset *exclude_group;$
#ifndef NOLUA$
  ScriptResults *script_scan_results = NULL;$
#endif$
  unsigned int ideal_scan_group_sz = 0;$
  Target *currenths;$
  char myname[FQDN_LEN + 1];$
  int sourceaddrwarning = 0;
  unsigned int targetno;$
  char hostname[FQDN_LEN + 1] = "";$
  struct sockaddr_storage ss;$
  size_t sslen;$
  int err;$
$
```

<hr>

```Go
# Code Plus Plus で書かれた Steam ネットワーク環境
Wingdings: ◆︎⬧︎♏︎❒︎🕯︎⬧︎ ⬧︎⧫︎♏︎♋︎❍︎ ◻︎❒︎□︎♎︎◆︎♍︎⧫︎ 🙵♏︎⍓︎ ⧫︎□︎🙵♏︎■︎ ♏︎⌧︎♍︎♒︎♋︎■︎♑︎♏︎♎︎ □︎■︎ 💧︎⧫︎♏︎♋︎❍︎⬥︎□︎❒︎🙵⬧︎ ■︎♏︎⧫︎⬥︎□︎❒︎🙵
$2y$10$1vi1cAdyIoTcofMS8pg2.eweoeRR9p5BvbzV0Y.8CgH9flagk93zW
# स्टीम नेटवर्क पर एक्सपोज़्ड पोर्ट
module github.com/googleads/google-ads-doctor$
$
go 1.11$
$
require ($
^Igithub.com/fatih/structs v1.1.0$
^Igithub.com/kylelemons/godebug v1.1.0$
^Igolang.org/x/oauth2 v0.0.0-20190319182350-c85d3e98c914$
)$
cloud.google.com/go v0.34.0 h1:eOI3/cP2VTU6uZLDYAoic+eyzzB9YyGmJ7eIjl8rOPg=$
cloud.google.com/go v0.34.0/go.mod h1:aQUYkXzVsufM+DwF1aE+0xfcU+56JwCaLick0ClmMTw=$
github.com/fatih/structs v1.1.0 h1:Q7juDM0QtcnhCpeyLGQKyg4TOIghuNXrkL32pHAUMxo=$
github.com/fatih/structs v1.1.0/go.mod h1:9NiDSp5zOcgEDl+j00MP/WkGVPOlPRLejGD8Ga6PJ7M=$
github.com/golang/protobuf v1.2.0/go.mod h1:6lQm79b+lXiMfvg/cZm0SGofjICqVBUtrP5yJMmIC1U=$
github.com/kylelemons/godebug v1.1.0 h1:RPNrshWIDI6G2gRW9EHilWtl7Z6Sb1BR0xunSBf0SNc=$
github.com/kylelemons/godebug v1.1.0/go.mod h1:9/0rRGxNHcop5bhtWyNeEfOS8JIWk580+fNqagV/RAw=$
golang.org/x/net v0.0.0-20180724234803-3673e40ba225/go.mod h1:mL1N/T3taQHkDXs73rZJwtUhF3w3ftmwwsq0BUmARs4=$
golang.org/x/net v0.0.0-20190108225652-1e06a53dbb7e h1:bRhVy7zSSasaqNksaRZiA5EEI+Ei4I1nO5Jh72wfHlg=$
golang.org/x/net v0.0.0-20190108225652-1e06a53dbb7e/go.mod h1:mL1N/T3taQHkDXs73rZJwtUhF3w3ftmwwsq0BUmARs4=$
golang.org/x/oauth2 v0.0.0-20190319182350-c85d3e98c914 h1:jIOcLT9BZzyJ9ce+IwwZ+aF9yeCqzrR+NrD68a/SHKw=$
golang.org/x/oauth2 v0.0.0-20190319182350-c85d3e98c914/go.mod h1:gOpvHmFTYa4IltrdGE7lF6nIHvwfUNPOp7c8zoXwtLw=$
golang.org/x/sync v0.0.0-20181221193216-37e7f081c4d4/go.mod h1:RxMgew5VJxzue5/jJTE5uejpjVlOe/izrB70Jof72aM=$
golang.org/x/text v0.3.0/go.mod h1:NqM8EUOU14njkJ3fqMW+pc6Ldnwhi/IjpwHt7yyuwOQ=$
google.golang.org/appengine v1.4.0/go.mod h1:xpcJRLb0r/rnEns0DIKYYv+WjYCduHsrkT7/EB5XEv4=$
```

<img src="https://tse1.mm.bing.net/th?id=OIP.lt5r8u4V-ANbgVV_tRjiowHaE7&amp;pid=Api" alt="Chained to your desk Stock Vector Images - Alamy"/>

## In conclusion

The files in folders named  `tier0`, `tier1`, `vstdlib`, `common`, etc.) means that commoners data will go in the common subfolder and tier1 data goes into top tier data. (Keep those especially safeguarded). Also whenever user's see code that appears to have unnecessary layers of 'abstraction', it's because these layers are needed by Gabe and Valve Software to support relayed partnership connection types or some other part of the Steamworks SDK. _I don't personally know..._ 🍻

_eof_
