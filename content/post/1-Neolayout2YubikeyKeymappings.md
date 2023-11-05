---
title: "Neolayout2 Yubikey Keymappings"
date: "2023-11-05T15:22:37Z"
draft: false
pin: false  <!--Do you want to pin this blog post? (true/false)-->
summary: Neolayout2 Yubikey Keymappings <!--Blog post visible summary here-->
--- 
<!--Blog content here-->
[Neolayout2](https://neo-layout.org/) is a rather esoteric ergonomic keyboard layout optimized for the German language. Except for the numbers, nearly all keys are mapped in a non-standard way not even remotely similar to qwerty or qwertz keyboard layouts.

Luckily, Linux supports this keyboard layout out of the box. But this poses problems when generating OTP passwords from a [Yubikey](https://www.yubico.com/), which emulates an USB keyboard. The key presses the Yubikey sends to the host PC are mapped to different characters by the keyboard layout, which the Yubikey knows nothing about. This leads to OTP passwords starting with ääääää instead of cccccc as it should be.

The Yubikey tries to circumvent the problem of variable keyboard layouts on the host PC by using only keys that are the same on qwerty, qwertz and Dvorak layouts, but this approach fails on more esoteric layouts. But using the ykpersonalize tool, one can set a custom mapping for the 45 keys used by the Yubikey NEO or newer, so that after mapping through the host PC keyboard layout, the expected characters end up in the OTP password.

The command to make a Yubikey emit correct keypresses for the [neolayout2](https://neo-layout.org/) keyboard layout is 


