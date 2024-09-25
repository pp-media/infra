# Specifications for PP32 media setup

## Video

**Production**
1080p50 @ 3G (3G-SDI, HDMI)

**Mezzanine**
1080p50 @ 50 Mbps (or 20 Mbps, depending on what works)

**Live delivery**
Twitch RTMP to polarparty

*@kfh has credentials for login*

* Encoder spec
    * 1080p50 @ 12 Mbps (or 6 Mbps -- need to test)
    * h264
    * Rate: CBR
    * Keyframe interval: 2 sec/100 frames
    * Profile: High
    * Audio: AAC-LC Stereo @ 160 kbps
* Ingest URL: rtmp://osl.contribute.live-video.net/app/{stream_key}

**VOD delivery**
YouTube to polarpartyno

* 1080p50
* ProRes 422 HQ (best Youtube can ingest)
    * Needs to be tested -- review if it doesn't work

**Live flow**

```
                                                             ----------------
                                                            |   Transcoder   |
                                                             ----------------
                                                              /|\          |
                                                               |         Twitch
                                                           mezzanine    delivery   
                                                               |          \|/
 -----------     PGM      -------------------                 ----------------     Twitch     --------
| Mix, ATEM | - 3G SDI > | BMD Web presenter | - mezzanine > | RTMP reflector | - delivery > | Twitch |
 -----------      |       -------------------                 ----------------                --------
                 \|/                                           |           |            
          ----------------                                 mezzanine     Twitch       
         | Matrox Monarch |                                    |        delivery   
         | record to HDD  |                                   \|/         \|/             Copy/backup
         |    (backup)    |                                    --------------             -----------
          ----------------                                    | Dump to disk | - files > | Media NAS |
                                                               --------------             -----------
```

## Infra

* OS: Debian 12.7.0
* Provisioning: PXE from RPi
* Config mgmg: Ansible playbooks
* Secret management: Ansible Vault
