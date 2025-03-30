# KioskBreakout
This HTML page contains functionality to assist pentesters in escaping restricted browser environments and access the underlying windows OS. The page is entirely self-contained and includes no external dependencies making it suitable for usage against targets with limited or no outbound internet access.

# Rational 
There are several websites that offer similar functionality such as the classic ikatz breakout tool and phrack.me kiosk evasion tool. While these are excellent resources, sometimes you will not be able to perform arbitrary navigation to third-party sites from your kiosk target. In situations where internet access is restricted or severely filtered, it may be necessary for testers to have a self-contained, offline version of these tools with similar functionality. This kiosk breakout assisstant fills that requirement.

# Usage
Simply load this html file in the kiosk browser somehow, and you can begin attempting to breakout using the functionality built-in to the page. There are currently 5 main sections.

1. **JavaScript Console** : Lets you run arbitrary javascript from the page itself, useful when developper tools / inspect element are disabled2.
2. **ActiveX Console** : Lets you run arbitrary os level commands from the page. This will not work in modern browsers, but is useful if you can somehow get the page to load in IE. 
3. **Common Dialogues** : A few common web features that may let you open an explorer context even when keyboard shortcuts are disabled (upload file, save as, print, etc.).
4. **Chromium Settings** : These are pseudo-protocol urls that open various settings in chromium-based browsers (Edge, Chrome, Opera, Brave, etc.). Browser security forces us to copy paste these into the URL bar.
5. **Protocol Handlers** : This is a huge list of protocol handler links that may trigger an explorer dialogue or otherwise launch another application that presents breakout possibilities.

# Protip
If you are wondering how to get this page into your target environment, consider using a data-uri! Encoding the entire page a data:text/html uri is an effective way to circumvent data infiltration countermeasures. If you do not have access to the clipboard, no worries. I have another project called [sloppyCopy](https://github.com/PN-Tester/sloppyCopy) which can get this file into a restricted environment in less than 3 minutes via keyboard simulation. Simply point SloppyCopy at KioskBreakout.html and use the ```--citrix``` and ```--uri``` flags.
