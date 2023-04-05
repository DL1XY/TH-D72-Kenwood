# TH-D72-Kenwood - PC RIG control commands
## DL1XY
### How to connect TH-D72 in serial mode 
* Make sure you have firmware v1.10 installed
* Connect TH-D72 via USB cable to your PC
* Turn TH-D72 on, make sure you are not in TNC mode
* Run `lsusb`, you should see `Silicon Labs CP210x UART Bridge` somewhere
* Check if you find `/dev/ttyUSB0` or `/dev/ttyUSB1`, this should be your TH-D72
* Start `putty` or any other terminal tool which can do serial communication.
* Use this configuration:
  * Connection type: `Serial`
  * Serial line: `/dev/ttyUSB0`
  * Speed: `9600`
  * Data bits: `8`
  * Stop bits: `1`
  * Parity: `None`
  * Flow control: `None`
* Start the session

That"s all, now you can send the commands described here. If you type in `FO 1` and press Enter, you should see the VFO configuration of Band B like `FO 1,0430000000,7,0,0,0,0,0,0,08,08,000,0,01600000,0`.

#### Important
* TH-D72 sends a questionmark `?` if it doesn't know the command you sent
* There is **no** new line after sending/receiving a command

### How to connect TH-D72 in TNC mode 
* Follow the steps in **How to connect TH-D72 in serial mode**
* Press `TNC` key several times until you see something like the following text in the terminal window.
```
bbRAM loaded with defaults



Kenwood Radio Modem
AX.25 Level 2 Version 2.0
Release 16/Nov/2010 2Chip Version 1.00
Checksum $7772
cmd:DA 230307131728
cmd:MY NOCALL
MYCALL   was NOCALL
cmd:
```
* Now you are in TNC mode and you can execute the commands as described in the manual.

#### Important
* TH-D72 sends a questionmark followed by EH `?EH` in TNC mode if it doesn't know the command you sent
* TH-D72 is ready for TNC commands if `cmd:` appears in terminal

## LA3QMA
Reverse engineered commands based on my first discovery for the TM-D710.
https://github.com/LA3QMA/TH-D72-Kenwood/wiki

### Please report any errors as this has been converted from my old documents.
https://kenwood-radios.groups.io/g/main/messages and https://kenwood-radios.groups.io/g/TH-D72

Available Control commands: (Firmware V1.10) (incl implementation marks by DL1XY, #1 OK: Command implemented, #2 OK: Unittest implemented)

- ID	[Radio Model](/commands/ID.md) :ok: :ok:
- AE	[Radio serialnumber](/commands/AE.md) :ok: :ok: 
- FV	[Firmware version](/commands/FV.md) :ok: :ok:
- TY	[Radio Type](/commands/TY.md) :ok:
- DL	[Dual Band Mode/Single Band Mode](/commands/DL.md) :ok: :ok:
- MR	[Memory channel](/commands/MR.md) :ok: :ok:
- ME	[Memory channel, frequency, offset etc](/commands/ME.md) :ok: :ok:
- FO	[VFO channel](/commands/FO.md) :ok: :ok:
- BC	[PTT and CTRL Band](/commands/BC.md) :ok: :ok:
- VM	[Memory/VFO](/commands/VM.md) :ok:
- DW	[Emulates the Microphone Down Key](/commands/DW.md) :ok: :ok:
- UP	[Emulates the Microphone Up Key](/commands/UP.md) :ok:
- PC	[Output power](/commands/PC.md) :ok:
- SQ	[Squelch status](/commands/SQ.md) :ok:
- BY	[Squelch open/closed](/commands/BY.md) :ok: :ok:
- RX	[Receive](/commands/RX.md) :ok:
- TX	[Transmit](/commands/TX.md) :ok:
- BT	[Burst tone](/commands/BT.md) :ok: :ok:
- RT	[Time](/commands/RT.md) :ok:
- GP	[Internal GPS](/commands/GP.md) :ok: :ok:
- GM	[Radio/GPS](/commands/GM.md) :ok: :ok:
- TN	[TNC status](/commands/TN.md) :ok:
- ~~AS	[Reverse](/commands/AS.md)~~ - removed in Firmware V1.08
- CS	[Callsign](/commands/CS.md) :ok: :ok:
- SR	[Reset](/commands/SR.md) :ok:
- CC	[CALL channel](/commands/CC.md) :ok: :ok:
- LK	[Key Lock](/commands/LK.md) :ok: :ok:
- PV	[Programmable VFO](/commands/PV.md) :ok:
- MN	[Memory name](/commands/MN.md) :ok: :ok:
- MS	[Power on message](/commands/MS.md) :ok: :ok:
- TT	[Transmit tone](/commands/TT.md) :ok:
- ~~CD	[*Channel status*](/commands/CD.md)~~ - removed in Firmware V1.08
- DM	[DTMF memory](/commands/DM.md) :ok: :ok:
- ~~SS	[*S-meter squelch*](/commands/SS.md)~~- only ? as response
- DT	[DTMF](/commands/DT.md) :ok: :ok:
- BA	[Battery type](/commands/BA.md) :ok: :ok:
- BL [Backlight](/commands/BL.md) :ok: :ok: :arrow_forward: **check setter again** 
- MU	[Menu](/commands/MU.md) :ok:
- TC	[TNC controll mode](/commands/TC.md) :arrow_forward: **check setter again, strange behaviour**
- TS	~~[TNC controll mode 2](/commands/TS.md)~~ only ? as response but RCVD when TC or TC 0
- PROGRAM		[0M PROGRAM : Enters MCP programming mode](/commands/0M_PROGRAM.md) (Command is: ZERO MIKE space PROGRAM)
- SERVICE	[0G KENWOOD : Enters service mode](/commands/0G_KENWOOD.md) (Command is: ZERO GOLF space KENWOOD)
