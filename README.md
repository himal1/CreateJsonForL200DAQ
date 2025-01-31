# CreateJsonForL200DAQ
Create Json file for the DAQ machine at LNGS for L200 experiment 
Here is the corresponding data in detector google sheet for each column in ORCA configuration file.
**1. For the Ge detector:**
		Name in configuration → identification in ORCA → Name in detector sheet
	Detector
	1. Serial → serial → 1st Column with no name
	2. Type → det_type → 7 digit detector name starts with P, B and V are ppc, bage and icpc respectively
	String Layout
	1. Str → str_number → String
	2. Pos → str_position → Position
	FlashCAM DAQ
	1. Crate → daq_crate → Flashcam (1st number is crate. eg: 1G5-2; 1 is crate #, G means Ge Det, 5 is slot number, and 2 is channel number)
	2. Address → daq_board_id → check ORCA window to see which Flashcam is connected in which slot (check hardware at LNGS to be 100% sure)
	3. Slot → daq_board_slot → Flashcam (2nd number is slot. eg: 1G5-2; 1 is crate #, G means Ge Det, 5 is slot number, and 2 is channel number)
	4. Chan → daq_board_ch → Flashcam (3rd number after dash is channel. eg: 1G5-2; 1 is crate #, G means Ge Det, 5 is slot number, and 2 is channel number)
	High Voltage
	1. Crate → hv_crate → HV crate is always 0 in L200 
	2. Slot → hv_board_slot → HV Module 
	3. Chan → hv_board_chan → HV Channel
	4. Cable → hv_cable → kept blank in L200 (--)
	5. Flange ID → hv_flange_id → HV Flange
	6. Flange Pos → hv_flange_pos → HV Feedthrough (remove dots)
	Front-End Electronics
	1. CC4 → fe_cc4_ch → use two input 'CC4'-'CC4-Channel
	2. Analog → fe_head_card_ana → Flange
	3. Digital → fe_head_card_dig → HE Addr
	4. Fanout → fe_fanout_card → HE Cable
	5. RPi → fe_raspberrypi → RPi
	6. LMFE → fe_lmfe_id → LMFE
 
 
**2. For SiPMS (LAr Detector)**
		 Name in configuration → identification in ORCA → Name in detector sheet
	Detector
	1. Serial  → serial → SiPM ID (with addition of 'S' in front of SiPM ID)
	2. Type → det_type → Fiber ID (without number after -) 
	FlashCam DAQ
	1. Crate → daq_crate → Crate
	2. Board ID → daq_board_id → check ORCA window to see which Flashcam is connected in which slot (check hardware at LNGS to be 100% sure)
	3. Slot → daq_board_slot → Slot
	4. Chan → daq_board_chan → Ch
	Low Voltage
	1. LV Crate → lv_crate → not updated yet
	2. LV Chan → lv_board_chan → not updated yet
	3. LV Slot → lv_board_slot → not updated yet
	4. Barrel Pos → lv_board_B_pos →use Angle to obtain this information
	5. Loc → lv_board_string → need to obtain usinf information : 'if Fiber ID starts with IB or OB' and 'if later part of Fiber ID is divisible 2 or not' (1→ top outer barrel; 2→ top inner barrel 3→ bottom inner barrel, 4→ bottom outer barrel)