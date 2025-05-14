# Cisco Enterprise Endpoints

Cisco Entprise Endpoints (SIP and SCCP) are supported on the LTS Community PBX. HOWEVER, there are some caveats.

Cisco Enterprise phones running SCCP frimware can be provisoined to our system over the SCCP protocol. However, you must have a separate extension for your SCCP phones, you cannot mix SCCP and SIP devices on one extension. But you can have any amount of SCCP phones you want on a single extension. Most of the phones server-side features will work.

Cisco Enterprise phones running SIP frimware can also be used on our system with a CHAN_SIP or PJSIP extension. When used with CHAN_SIP, the phone can recvive incoming calls, use BLFs, call fowarding, call history, transfer, and other server-side features, however CHAN_SIP can only be used with one phone at a time. PJSIP can be used with more then one phone and will work with Cisco SIP phones, however incoming calls, BLFs, call fowarding, call history, transfer, and other server-side features will not work. Also calls will not auto hang-up when it ends.

Cisco Enterpise Phone support is provided as is. If you would like a Cisco phone that will work with other SIP phones on the same extension, you will need a SPA series or 6800/7800/8800 series phone running 3PCC frimware. 