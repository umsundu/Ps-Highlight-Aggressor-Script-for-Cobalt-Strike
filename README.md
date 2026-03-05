# ps-highlight.cna

Aggressor script for Cobalt Strike that colour codes the output of `ps` to make it easy to spot EDR, browsers, admin tools and your current beacon process at a glance.

Based on the original work by [@r3dQu1nn](https://github.com/harleyQu1nn/) and [@oldb00t](https://github.com/oldb00t). Rewritten because the original was causing Cobalt Strike instability. Added a separate category for SIEM and threat hunting agents since spotting those is just as important as spotting EDR.

## Colours

| Colour | Meaning |
|--------|---------|
| Red | AV/EDR process |
| Orange | SIEM/IR/Threat hunting agent |
| Yellow | Your current beacon |
| Blue | explorer.exe / winlogon.exe |
| Green | Browser |
| Light Blue | Admin/IR tool |

## EDR Coverage (Red)

CrowdStrike, SentinelOne, Microsoft Defender/MDE, Carbon Black, Cylance, Cortex XDR, Sophos, ESET, Kaspersky, Trellix/McAfee, Symantec, Tanium, Cybereason, Elastic Endgame, Qualys, Rapid7, Bitdefender, Malwarebytes, Webroot, F-Secure/WithSecure, Huntress, Cynet, Deep Instinct, Fortinet, Avast/AVG, FireEye HX, Wazuh, OSSEC and more.

## SIEM / IR / Threat Hunting Coverage (Orange)

Velociraptor, osquery, Elastic Agent/Beats, Splunk Universal Forwarder, NXLog, Graylog Sidecar, Fluentd, Fluent Bit, Logstash, Azure Monitor Agent, Sysmon, Humio/Falcon LogScale, Cribl, Datadog Agent.

Seeing orange processes means logs are being shipped somewhere or the blue team has active hunting capability. Velociraptor and osquery in particular mean someone can hunt across the estate on demand. Factor that into your opsec decisions before doing anything noisy.

## Usage

Load via `View > Script Manager > Add` then just run `ps` in your beacon console as normal.

## Notes

If you want to add processes to any of the lists just drop them into the relevant array at the top of the script.

`agent.exe` is included for Datadog but it's a generic name and may produce false positives. Remove it and keep `datadog-agent.exe` if it becomes noisy.

