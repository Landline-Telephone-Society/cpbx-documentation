# Asterisk

You can connect Asterisk to the LTS Community PBX as a trunk over SIP or IAX.
## Configuring trunk over SIP using CHAN_PJSIP

### Loading chan_pjsip
chan_pjsip and all the resource modules relating to PJSIP should be installed and loaded. It should be loaded if you have autoload enabled in modules.conf, however you may check by running "module show like pjsip" within the Asterisk CLI (asterisk -r), it should look something like this:

```
communitypbx*CLI> module show like pjsip
Module                         Description                              Use Count  Status      Support Level
chan_pjsip.so                  PJSIP Channel Driver                     0          Running              core
func_pjsip_endpoint.so         Get information about a PJSIP endpoint   0          Running              core
res_pjsip.so                   Basic SIP resource                       38         Running              core
res_pjsip_acl.so               PJSIP ACL Resource                       0          Running              core
res_pjsip_authenticator_digest.so PJSIP authentication resource            0          Running              core
res_pjsip_caller_id.so         PJSIP Caller ID Support                  1          Running              core
res_pjsip_dialog_info_body_generator.so PJSIP Extension State Dialog Info+XML Pr 0          Running              core
res_pjsip_diversion.so         PJSIP Add Diversion Header Support       1          Running              core
res_pjsip_dtmf_info.so         PJSIP DTMF INFO Support                  0          Running              core
res_pjsip_endpoint_identifier_anonymous.so PJSIP Anonymous endpoint identifier      0          Running              core
res_pjsip_endpoint_identifier_ip.so PJSIP IP endpoint identifier             0          Running              core
res_pjsip_endpoint_identifier_user.so PJSIP username endpoint identifier       0          Running              core
res_pjsip_exten_state.so       PJSIP Extension State Notifications      0          Running              core
res_pjsip_header_funcs.so      PJSIP Header Functions                   0          Running              core
res_pjsip_logger.so            PJSIP Packet Logger                      0          Running              core
res_pjsip_messaging.so         PJSIP Messaging Support                  0          Running              core
res_pjsip_mwi.so               PJSIP MWI resource                       0          Running              core
res_pjsip_mwi_body_generator.so PJSIP MWI resource                       0          Running              core
res_pjsip_nat.so               PJSIP NAT Support                        0          Running              core
res_pjsip_notify.so            CLI/AMI PJSIP NOTIFY Support             0          Not Running          core
res_pjsip_one_touch_record_info.so PJSIP INFO One Touch Recording Support   0          Running              core
res_pjsip_outbound_authenticator_digest.so PJSIP authentication resource            0          Running              core
res_pjsip_outbound_publish.so  PJSIP Outbound Publish Support           2          Running              core
res_pjsip_outbound_registration.so PJSIP Outbound Registration Support      0          Running              core
res_pjsip_path.so              PJSIP Path Header Support                0          Running              core
res_pjsip_pidf_body_generator.so PJSIP Extension State PIDF Provider      0          Running              core
res_pjsip_pidf_digium_body_supplement.so PJSIP PIDF Sangoma presence supplement   0          Running              core
res_pjsip_pidf_eyebeam_body_supplement.so PJSIP PIDF Eyebeam supplement            0          Running              core
res_pjsip_publish_asterisk.so  PJSIP Asterisk Event PUBLISH Support     0          Running              core
res_pjsip_pubsub.so            PJSIP event resource                     95         Running              core
res_pjsip_refer.so             PJSIP Blind and Attended Transfer Suppor 1          Running              core
res_pjsip_registrar.so         PJSIP Registrar Support                  0          Running              core
res_pjsip_rfc3326.so           PJSIP RFC3326 Support                    0          Running              core
res_pjsip_sdp_rtp.so           PJSIP SDP RTP/AVP stream handler         0          Running              core
res_pjsip_send_to_voicemail.so PJSIP REFER Send to Voicemail Support    0          Running              core
res_pjsip_session.so           PJSIP Session resource                   15         Running              core
res_pjsip_t38.so               PJSIP T.38 UDPTL Support                 0          Running              core
res_pjsip_transport_websocket.so PJSIP WebSocket Transport Support        0          Running              core
res_pjsip_xpidf_body_generator.so PJSIP Extension State PIDF Provider      0          Running              core
39 modules loaded

```
Just to be sure, you should add the PJSIP modules to modules.conf to ensure they load. All modules relating to pjsip should have been installed by default when you complied Asterisk. To set the pjsip modules to load, add the following to modules.conf:

```
load = chan_bridge_media.so
load = chan_pjsip.so
load = func_pjsip_endpoint.so
load = res_pjproject.so
load = res_pjsip_acl.so
load = res_pjsip_authenticator_digest.so
load = res_pjsip_caller_id.so
load = res_pjsip_dialog_info_body_generator.so
load = res_pjsip_diversion.so
load = res_pjsip_dtmf_info.so
load = res_pjsip_endpoint_identifier_anonymous.so
load = res_pjsip_endpoint_identifier_ip.so
load = res_pjsip_endpoint_identifier_user.so
load = res_pjsip_exten_state.so
load = res_pjsip_header_funcs.so
load = res_pjsip_logger.so
load = res_pjsip_messaging.so
load = res_pjsip_mwi_body_generator.so
load = res_pjsip_mwi.so
load = res_pjsip_nat.so
load = res_pjsip_notify.so
load = res_pjsip_one_touch_record_info.so
load = res_pjsip_outbound_authenticator_digest.so
load = res_pjsip_outbound_publish.so
load = res_pjsip_outbound_registration.so
load = res_pjsip_path.so
load = res_pjsip_pidf_body_generator.so
load = res_pjsip_pidf_digium_body_supplement.so
load = res_pjsip_pidf_eyebeam_body_supplement.so
load = res_pjsip_publish_asterisk.so
load = res_pjsip_pubsub.so
load = res_pjsip_refer.so
load = res_pjsip_registrar.so
load = res_pjsip_rfc3326.so
load = res_pjsip_sdp_rtp.so
load = res_pjsip_send_to_voicemail.so
load = res_pjsip_session.so
load = res_pjsip.so
load = res_pjsip_t38.so
load = res_pjsip_transport_websocket.so
load = res_pjsip_xpidf_body_generator.so
load = res_rtp_asterisk.so
```

A few above modules such as res_rtp_asterisk are not part of pjsip, but may be necessary depending on your setup. If you already have them loaded, you can safely skip them.

Then once added, you can restart Asterisk. While you can manually load the modules, it's probably better to restart Asterisk entirely.


### Configuring PJSIP

pjsip and all it's endpoints are configured in pjsip.conf.

If you don't already have pjsip configured, add the following to pjsip.conf:

```

[global]
type=global
use_callerid_contact=no
debug=no
keep_alive_interval=90
default_outbound_endpoint=dpma_endpoint
endpoint_identifier_order=ip,username,anonymous,header,auth_username
taskprocessor_overload_trigger=pjsip_only

[transport-udp]
type=transport
protocol=udp
bind=0.0.0.0:5060      ; If you already have CHAN_SIP loaded using port 5060, you will likey want to change your bind port.

[transport-tcp]
type=transport
protocol=tcp
bind=0.0.0.0:5060      ; If you already have CHAN_SIP loaded using port 5060, you will likey want to change your bind port.

```
If you have issues with RTP, you may need to define your external media/signaling address:

```
external_media_address=YOUR IP
external_signaling_address=YOUR IP
```

Replace "YOUR IP" of the IP address of the Asterisk box. Generally, if Asterisk is on a system in-front of NAT and all the phones are on the same network, then your private IP is fine. If the system is a VPS or has no firewall, then use your public IP.

For sanity purposes, some people prefer to have config for endpoints in separate files. If you wish to do this, you can create seperate files (for example pjsip_trunks.conf and pjsip_extensions.conf), then include them in pjsip.conf. When you include the files, Asterisk will see all 3 files as one big file, but it makes it easier for you to manage. To include a file, use:

```
#include filename
```

### Configuring the trunk

To configure the trunk, add the following to your pjsip config:

```
[LTSCPBX]
type=auth
auth_type=userpass
password=EXTENSIONPASSWORD
username=YOUREXTENSION

[LTSCPBX]
type=endpoint
transport=transport-tcp       ; You can also use UDP if you wish. If you use your own transport, set it here.
context=from-ltscpbx          ; This goes along with the example dialplan context below.
disallow=all
allow=g722,ulaw,h264          ; You can set the codecs you wish to support here. These are the most common ones for North American standards, which is what the LTS Community PBX uses.
aors=LTSCPBX
send_connected_line=false
outbound_auth=LTSCPBX
user_eq_phone=no
t38_udptl=no
t38_udptl_ec=none
fax_detect=no
trust_id_inbound=no
t38_udptl_nat=no
direct_media=no
rtp_symmetric=yes
dtmf_mode=auto

[LTSCPBX]
type=aor
qualify_frequency=60
contact=sip:YOUREXTENSION@communitypbx.landlinetelephonesociety.com:5060   ; 17777 is also available as an alternate PJSIP port on the LTS Community PBX if you cannot use outbound 5060.
```


## Adding trunk over SIP using CHAN_SIP
CHAN_SIP is long deprecated and no longer maintained, and you should only be using CHAN_PJSIP if possible especially for trunks. Theres no reason you should be using CHAN_SIP trunks on new Asterisk deployments. However, these insturctions are provided so if for some reason you want to use CHAN_SIP. Even if your using CHAN_SIP on your end, you should use your extensions PJSIP endpoint on our end.

### Loading CHAN_SIP.

On newer verisons of Asterisk, CHAN_SIP usually does not autoload. To load CHAN_SIP, add the following to modules.conf:

```
load = chan_sip.so
```
Once added, restart Asterisk. Then go into the asterisk console using asterisk -r and run "module show like chan_sip". You should see:

```
communitypbx*CLI> module show like chan_sip
Module                         Description                              Use Count  Status      Support Level
chan_sip.so                    Session Initiation Protocol (SIP)        0          Running        deprecated
1 modules loaded
```

### Configuring CHAN_SIP

CHAN_SIP is configured in sip.conf. Below is a super minimal config file.

```
[general]
context=from-internal
allowguest=no
allow=g722
allow=ulaw
allow=alaw
disallow=all
udpbindaddr=0.0.0.0:5160   ; If for some reason you are making CHAN_SIP your primary SIP channel driver, change this to 5060.
nat=force_rport,comedia
externip=IPADDR            ; Use the IP of your Asterisk box.
```

Just like shown above in the PJSIP conifg, you can also if you wish, include files for your SIP devices and trunks.

### Adding the trunk


## Adding trunk over IAX using CHAN_IAX2

## Setting up the Dialplan

The dialplan is how calls are routed in Asterisk. Above in the trumk, we used 
