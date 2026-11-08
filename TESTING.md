# Hardware test log

Target device: Toshiba 50UV1553DB, VIDAA, Europe region.

Rule: a claim counts as verified only with a row in the session log below -
date, firmware version, step, expected result, observed result, reverted
(yes/no). Everything else is a sourced claim, labeled as such.

## Status table

| Claim | Source | Status on UV1553DB |
|---|---|---|
| VIDAA has no ADB, no sideloading, no package list | cleanyourtv.wiki, justatv.eu | Consistent across all sources; to be re-confirmed on device |
| Privacy settings exist and are reversible | vidaa.com policy, justatv.eu, velmo.one | Menu names unverified on this model |
| Upstream blocklist cleans the home screen, YouTube/Netflix keep working | ipanalytics (Hisense, Germany) | Not tested on Toshiba |
| MQTT local control works on Toshiba VIDAA | warrenrees/ha_vidaatv README | Not tested on this model |

The step-by-step protocol for the first session is [docs/05-first-hardware-session.md](docs/05-first-hardware-session.md).

## Session log

The 2026-11-08 rows are a partial session on a Hisense 65A67H, not the
target device: menu names and the after-checks were confirmed by the owner,
but the firmware version is still missing, so they do not yet meet the rule
above.

| Date | Firmware | Step | Expected | Observed | Reverted |
|---|---|---|---|---|---|
| 2026-11-08 | Not recorded (Hisense 65A67H, VIDAA U6) | Settings → Advanced settings → Enhanced viewing settings → Enable Automatic Content Recognition → Off | Menu present as in the U6 manual | Reported by owner: present with that name, switched off | No |
| 2026-11-08 | Not recorded (Hisense 65A67H, VIDAA U6) | Device usage data, App usage data collection → Off | Present next to ACR | Reported by owner: present, switched off | No |
| 2026-11-08 | Not recorded (Hisense 65A67H, VIDAA U6) | Settings → System → Advanced settings → Personalised Ads → Off, Reset Ads ID | Present as in the U6 manual | Reported by owner: present, switched off and reset | No |
| 2026-11-08 | Not recorded (Hisense 65A67H, VIDAA U6) | Settings → Support → Disclaimer and Privacy → EULA and Other Policy and Services | Consents listed and can be withdrawn | Reported by owner: matched, consents withdrawn | No |
| 2026-11-08 | Not recorded (Hisense 65A67H, VIDAA U6) | After-check: apps, HDMI inputs, YouTube, Netflix | Still working after the settings pass | Reported by owner: all working | No |
