__Set/Read the VFO channel__

Set the VFO channel:

	FO p1, p2, p3, p4, p5, p6, p7, p8, p9, p10, p11, p12, p13, p14, p15

Read the VFO channel:

	FO x
	
Returns: the configuration of VFO channel

`FO 1,0430000000,7,0,0,0,0,0,0,08,08,000,0,01600000,0`


|p|function|
|---|---|
|1|[Band](/tables/band.md)
|2|Frequency in Hz 10 digit. must be within selected band
|3|[Step size](/tables/step_size.md)
|4|[Shift direction](/tables/shift.md)
|5|[Reverse](/tables/status.md)
|6|[Tone status](/tables/status.md)
|7|[CTCSS status](/tables/status.md)
|8|[DCS status](/tables/status.md)
|9|[Split tone/CTCSS/DCS status](/tables/status.md)
|10|[Tone frequency](/tables/tone_ctcss.md)
|11|[CTCSS frequency](/tables/tone_ctcss.md)
|12|[DCS frequency](/tables/dcs.md)
|13|[Cross tone encode/decode]
|14|Offset frequency in Hz 8 digit
|15|[Mode](/tables/mode.md)
