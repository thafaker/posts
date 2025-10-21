---
title: Options for using Windows 11 with Mac® computers with Apple® M1®, M2™, and M3™ chips
slug: options-for-using-windows-11-with-mac-r-computers-with-apple-r-m1-r-m2-and-m3-chips
date_published: 1970-01-01T00:00:00.000Z
date_updated: 2024-01-25T06:43:08.000Z
draft: true
---

Microsoft erlaubt nun offiziell die Installation und Nutzung von Windows 11  auf Apple Silicon Macs, also derzeit dem M1, M2 und M3. Das finden wir cool, allerdings ging das schon immer und es gibt Einschränkungen, die man beachten sollte.

Der bisherige und nun von Microsoft frei gegebene Weg: Windows 11 via Parallels auf dem Mac installieren, dazu nahm man das Windows 11 for Arm Image und die restliche Magie lieferte die VM. Auch Apple erlaubt die Nutzung von Windows über diesen Umweg. Am Ende hatte man ein sehr gut und schnell laufendes Windows 11. 

Experiences that depend on an additional layer of virtualization (nested virtualization) are not supported, including:  

- [Windows Subsystem for Android](https://learn.microsoft.com/en-us/windows/android/wsa/), which enables your Windows 11 device to run Android applications that are available in the Amazon Appstore
- [Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/about), which enables a GNU/Linux environment on Windows 11
- [Windows Sandbox](https://learn.microsoft.com/en-us/windows/security/threat-protection/windows-sandbox/windows-sandbox-overview), a lightweight desktop environment to safely run applications in isolation
- [Virtualization-based Security (VBS)](https://learn.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-vbs), which enables customers to create and isolate a secure region of memory from the normal operating system
