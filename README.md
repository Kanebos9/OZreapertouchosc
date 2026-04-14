<img width="931" height="554" alt="OZ touchosc" src="https://github.com/user-attachments/assets/2b9011e9-4d44-4565-8a71-5417226da9ba" />

# OZreapertouchosc

TouchOSC template for Reaper. It controls the DAW itself to some extent and some specific plugins: ReaEQ, ReaComp, ReaGate, JS 1175, SSL G Master Buss Compressor, Alterboy, ProQ 4, H-Delay, L1+, Microshift, S1 Shuffler, Sibilance, Fresh Air, Decapitator, VintageVerb, Neural Amp Modeler. So you see, unfortunately it isn't flexible and won't fit most people's needs because it is tailored for specific plugins. But I think it gives great control and feedback for those who use these plugins. If not, feel free to use this project as your draft and personalize :)

TO SETUP

- First you need to have touchOSC (I used the latest one, not mk1) on a big tablet. I was testing this on a 10.4'' tablet (1280x768) and i don't think something smaller than that would be any good. And depending on your screen, you might need to stretch some boxes yourself.
  
- Copy the OZ.reaperOSC file i uploaded here. And paste it at username/appdata/roaming/reaper/OSC (The address is this on my w11 PC. Yours could be somewhere else).
  
- Go to Reaper > Options > Preferences > Control/OSC/web > Control Surface Mode > OSC. Pattern config should be chosen as the file you just copy/pasted. Device name can be whatever. Mode shuld be "Configure device IP+local port". Device port 9000 and local listen port 8000. Local ip is your computers ip anyway, device ip on the other hand, should be your tablets IP. If you're curious about what's different in this than the default reaperOSC, its just the device track number. Default was 8, i made it 40 (or 50 i dont remember).
  
- Install Realearn if you don't have it.
  
- Copy all the text inside the text file i uploaded here. Open Realearn on Reaper, click "Import from clipboard". It will automatically paste it itself. Save it as a preset (right next to where it says Main preset <none>) so you can access it easily later.
  
- If you haven't used touchosc before, also in Realearn, go to Input > Manage OSC Devices > New. Give it whatever name you like. And local port should be 8001, device port should be 9001 and device host should be your tablets IP address. Since we are assuming you haven't used it before; go to your tablets touchOSC connections settings too, choose OSC from left side, enable connection 1 and connection 2. Send and receive ports should be like this: in first one 8000 and 9000; second one 8001 and 9001. Both should be UDP and Zeroconf is Default. I don't know if other settings would work too but this one works so that's enough for us. Also don't forget, your tablet and computer must be connected to the same wifi.
  
- DONT FORGET: REALEARN MUST STAY ON IN EVERY PROJECT. MAKE SURE THE PRESET IS LOADED AND INPUT&OUTOUT OPTIONS ARE SELECTED WITH THE OSC SETTINGS WE JUST DID IN THE PREVIOUS STEP. SOMETIMES I TRY TO FIGURE OUT WHY THE TEMPLATE ISN'T WORKING PROPERLY ANYMORE. IT'S ALWAYS BECAUSE OF THIS.
  
- Extract the zip file I uploaded here (OZ scripts.7z). Copy all of the lua script files in it. Then go to Reaper > Actions (in the top bar) > Show action list > New action > Show reascript path in explorer/finder. It will open where your custom scripts are located. Paste all the lua files here. Then again, click on New action > Load reascript. Add all of them. Oh, and you dont have to choose one by one, you can select all of them at once, i didnt know that but now you know.
  
SOME DETAILS

- You can control 40 tracks + master tracks with this .tosc file. Whatever track is selected, all plugin controls focus on controlling that track.
  
- Preset next/previous buttons (under the track selection buttons) work for the last controlled FX, not the one thats floating currently on the screen. I made it that way because i thought i would need to control plugins without opening them.
  
- You might think that this button is mostly useless because some plugins dont share preset browser with reaper natively. But reaper has a way of adding preset on its own. Just tap on + on FX screen and add it. For example in Neural Amp Modeler, the presets you saved load the amp and ir files automatically so I think its actually very useful.
  
- The dual button in H-Delay is pretty annoying. It only accepts midi message. In realearn, you can send OSC messages as midi messages too. But you need to do the "midi learn" thing. So whatever i do wont matter, if you want it to work, you need to do it.
  
- All plugins give feedback to tablet except for reaeq. That's because i didnt choose realearn to program it. I referred to default reaperOSC file for it instead. The reason for that is, when you control a band frequency from your tablet for example, it adds that band automatically this way. Coudlnt do that in realearn. 
