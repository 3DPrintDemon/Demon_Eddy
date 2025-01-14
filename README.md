



# DEMON EDDY

Demonise your Eddy!

This file is for Eddy USB & Eddy Duo units using the probe as an virtual end stop with the beta offset function enabled ONLY!

It has been designed to run perfectly with the [Demon Klipper Essentials Unified](https://github.com/3DPrintDemon/Demon_Klipper_Essentials_Unified) macro pack!




> [!TIP]
> For full install & setup instructions of your Eddy probe head to the main [BTT EDDY repository here](https://github.com/bigtreetech/Eddy)

### INSTALL
Download the Demon_BTT_Eddy_Offset.cfg file above & drop it into your printer's config directory.

You can also use the command below via SSH:

```
cd ~/printer_data/config
wget https://raw.githubusercontent.com/3DPrintDemon/Demon_Eddy/refs/heads/master/Demon_BTT_Eddy_Offset.cfg --backups=1
```

### SETUP
1. Set the file to your requirements by entering the correct ID for your chosen interface.
2. Set the machine parameters for your printer, like bed mesh data, probe offset & any other settings you need.
3. Enable any optional sections or macros within the file that you might need. If using the file with the Demon Klipper Essentials Unified files you DO NOT need to do this!
4. Paste in the include command below into your printer.cfg file & restart Klipper.


```
[include ./Demon_BTT_Eddy_Offset.cfg]
```

> [!IMPORTANT]
> Make sure you have everything set up correctly & working before you try printing. Inproper setup & use can & will casue printer damage! This is on you.


Set your toolhead with the nozzle 20mm off the bed & run this command from the console:
```
LDC_CALIBRATE_DRIVE_CURRENT CHIP=btt_eddy
```
Save & restart

This sets the Eddy probe up so it can be used!

For a quick setup now send
```
PROBE_EDDY_CURRENT_CALIBRATE_AUTO CHIP=btt_eddy
```

Have some normal copy paper ready! Now with a FULLY COLD PRINTER place the paper under the nozzle & lower the nozzle to touch the paper (the nozzle must be perfectly clean with no old filament on it!), now BTT recommends you very slightly pinch the paper but I found you get better results to give it firm pressure without causing the paper to rip or be damaged in any way. You want the paper to be held by the nozzle but still movable both pushing & pulling. 

If you can't push the paper under the nozzle it’s too tight! You can experiment here.

Save & restart


Next while the printer is still cold follow the setup steps here for [thermal comensation](https://github.com/3DPrintDemon/Demon_Eddy?tab=readme-ov-file#5-temperature-compensation-calibration-eddy-usb-only)

If using an unenclosed printer use the stock values:
```
TEMPERATURE_PROBE_CALIBRATE PROBE=btt_eddy TARGET=56 STEP=4
```

If your printer is enclosed use these:
```
TEMPERATURE_PROBE_CALIBRATE PROBE=btt_eddy TARGET=70 STEP=5
```

After that....

Home your printer.

Lower your nozzle CAREFULLY to 2mm using the Mainsail move commands in the toolhead section.

Then place the paper under the nozzle & send the command 
```
G0 Z0
```
or lower the nozzle to Z0 with the move buttons, DO NOT use the Z-Offset adjust buttons! You will be very sorry if you do that!

Your piece of paper should still be moveable. Now use the mainsail Z-Offset adjsut buttons to correctly set your perfect Z-Offset! Light but definite pressure on the paper!

Now hit the little disk Save button in the toolhead Z_Offset section.

> [!IMPORTANT]
>Be VERY careful with your first print! Use an old bed surface or at least send a print with it off centre. If the Z offest needs adjusting do so & then hit save & retry!
