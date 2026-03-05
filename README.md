# ps-highlight.cna

Aggressor script for Cobalt Strike that colour codes the output of `ps` to make it easy to spot EDR, browsers, admin tools and your current beacon process at a glance.

Based on the original work by [@r3dQu1nn](https://github.com/harleyQu1nn/). Rewritten because the original was causing Cobalt Strike instability.

## Colours

| Colour | Meaning |
|--------|---------|
| Red | AV/EDR process |
| Yellow | Your current beacon |
| Blue | explorer.exe / winlogon.exe |
| Green | Browser |
| Light Blue | Admin/IR tool |

## EDR Coverage

CrowdStrike, SentinelOne, Microsoft Defender/MDE, Carbon Black, Cylance, Cortex XDR, Sophos, ESET, Kaspersky, Trellix/McAfee, Symantec, Tanium, Cybereason, Elastic Endgame, Qualys, Rapid7, Bitdefender, Malwarebytes, Webroot, F-Secure/WithSecure, Huntress, Cynet, Deep Instinct, Fortinet, Avast/AVG, FireEye HX and more.

## Usage

Load via `View > Script Manager > Add` then just run `ps` in your beacon console as normal.

## Notes

If you want to add processes to any of the lists just drop them into the relevant array at the top of the script.
