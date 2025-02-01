# THIS IS A WORK IN PROGRESS. INCOMPLETE. NO PROOFREADING DONE YET.

# XBOX CPU upgrade guide
Applying CPU upgrades to the original Xbox has been done since 2004. Yet, up until recently, resources and information to carry out this procedure have been hard to come by.
This guide aims to gather relevant information, tips and tricks all in one place to serve as a reference guide for performing this procedure properly, successfully, and repeatably.
Ideally, even newcomers should succeed on their first try.

# Tools
In order to carry out this procedure you require a fairly well-equipped workshop.
Listed below is the very minimum:
 - BGA station
 - hot-air station
 - (tacky) flux; preferably Amtech
 - soldering iron
 - tweezers
 - desoldering braid/wick
 - UV curable solder mask
 - 0.76mm solder balls
 - assortment of resistors
 - interposer board
 - [components for interposer board](https://htmlpreview.github.io/?https://raw.githubusercontent.com/zzattack/xbox-cpu-interposer/main/kicad/bom/ibom.html)
 - interposer aligntool pcb

# Motherboard preparations
Our target for today: a fresh 1.6 original Xbox console. Although differences are minor, this guide will also cover upgrades to non-1.6 revision boards.
![20250131_175006](https://github.com/user-attachments/assets/790b3587-39fa-436f-87a7-cf8dc972d661)

This guide will list all the steps taken to upgrade this console with a 1.4 GHz SL6BY CPU.
In general, any socket 370 CPU with 133MHz FSB will function correctly for this mod. The prefered CPUs to use are SL5XL and SL6BY since those are the only ones operating at 1.4 GHz. Some additional compatibility information can be found [here](https://github.com/N64-Freak/Xbox-CPU-interposer/tree/main/Hardware#choosing-a-processor).

## Removal from case
We start by removing the Xbox motherboard from its case. There's 6x torx-20 screws to remove from the bottom, followed by several torx-10 to get the board out. Several very [detailed writeups](https://www.se7ensins.com/forums/threads/dissassembling-your-xbox-an-in-depth-tutorial.6714/) can be found elsewhere with ease.

## Heatsink removal
First we remove the clamps holding the heatsinks in place. Using a screwdriver the clamps can be unlatched with minor force. I prefer to remove the GPU heatsink from the center of the board, and remove the CPU one from the edge:
![20250131_191352](https://github.com/user-attachments/assets/eaa12b53-67f8-47c5-99ef-7af10480881d)
![20250131_191318](https://github.com/user-attachments/assets/bd2268ba-78e0-44f8-b89b-687a3139bafe)
![20250131_191233](https://github.com/user-attachments/assets/d634a4ba-fc9a-41f7-8a26-a65962133fc7)

 The heatsinks can now be removed. If they feel stuck, do not apply force, since this is likely to strain the BGA balls underneath the chips. Use a hot-air gun for 20-30 seconds at high air speed, or just power on the xbox for a minute or two, and the heatsink should slide off with ease.
 ![20250131_191502](https://github.com/user-attachments/assets/4e6e9c67-cdbd-4f1f-ab14-3a348ce9d7fa)

 ### Heatsink bracket removal
 The next thing to remove is the heatsink bracket. We will be replacing this with a 3d printed one later on.

 I like to use side cutters to grip underneath the head of the plugs which expand the clips that go through the board. Do not slice the pins too deeply, we will be reusing them later on. As the blade edges slide underneath, you can pull up the clips with relative ease.
![20250131_191622](https://github.com/user-attachments/assets/ddccbf2b-ceb0-4cb1-99b8-f2fe451ed714)

Then, from the bottom, regular pliers can be used to push the clips up through the board.
![20250131_191807](https://github.com/user-attachments/assets/ebeb0b6a-45e5-45be-b465-29511ca46417)

With the bracket separated from the board, take out the clips which held it in place. Take care not to lose these.
![20250131_191957](https://github.com/user-attachments/assets/4053e017-9af0-4d45-a395-5abd8f994649)
![20250131_191914](https://github.com/user-attachments/assets/e4cfdfb3-159f-424c-91aa-6f3739891e8a)

The original bracket will not be reused and can be discarded.

## Thermal paste cleaning
The paste that was originally used for these machines isn't very effective. I don't bother removing the paste from the CPU since it gets replaced, but I do like to clean the GPU.
A purpose specific cleaning agent like Arctic Clean is highly effective at removing (any kind of) thermal paste, but generic solutions like isopropyl alcohol or goo-gone work well. If using goo-gone, rinse with alcohol afterwards.
![20250131_192016](https://github.com/user-attachments/assets/d02fc5db-dae0-4da0-8846-dc6ffb23ba1b)

Letting it soak for a minute increases its effectiveness significantly.
![20250131_192050](https://github.com/user-attachments/assets/34ea350c-39fb-4db6-afd4-eff533a6e43c)

Kimtech wipes are industry standard for good reason, but wiping with any lint-free cloth will do.
![20250131_192150](https://github.com/user-attachments/assets/f67f1493-bb86-441b-96d0-83f5d3eb8669)

Cleaned result, good as new.
![20250131_192317](https://github.com/user-attachments/assets/438de04a-21ee-43a3-851b-128028f9e838)

## Ultrasonic cleaning considerations
Boards were produced since 2000 and thus may have 25 years of gunk collected on them. Depending on the state of board, one may opt to (ultrasonically) clean it before working on it from a hygiene point of view. 
If the board collected primarily dust I will use compressed air to get rid of the worst.
I like to run the board through ultrasonic cleaning only once, so as a rule of thumb: if the board is nasty, clean it before working on it. Otherwise, run it through the ultrasonic after we're done.
Benefit of cleaning afterwards is that all flux residue left behind during our work gets cleaned up perfectly along.

## Baking
Right as you're getting excited to work on your upgrade, I urge you to exert patience. I'm unaware of the history of most boards coming in, and thus prefer to mitigate risk as much as possible. 
Boards stored in humid locations may have collected moisture. We'll be heating up the board significantly when replacing its CPU, which may lead to (violent) reactions within the board and/or chips mounted on it. 
Particularly the GPU is known to fail if no precautions are taken. Board warp is an additional concern.  
My recommendation is (at least) 12h of baking in an oven at about 90°C.

Conveniently, 3d printers with an enclosure typically have sufficient bed area and offer a filament drying option which suits this purpose adequately.
![20250201_002027](https://github.com/user-attachments/assets/07d0ba17-138c-4db8-8fb0-7dc5029896b7)


# CPU removal
With the motherboard fully prepared, we're positioned to begin the CPU replacement process.

## GPU heat shielding
The GPU is particularly susceptible to failure if improperly treated. I use aluminum tape to shield it from some of the heat generated during the BGA station cycles. Alternatively, kapton tape or isolating (silicone) thermal pads can be used as well.
![20250131_192655](https://github.com/user-attachments/assets/3717d6e9-4b6f-4f55-a760-069a550dfae3)

![20250131_192649](https://github.com/user-attachments/assets/4925860c-f3ca-47ff-ae3c-79cda5b24cbf)

## CPU lift
We'll now remove the CPU on the BGA station. The profile I'm using is shown below. It can serve as a starting point, but is by no means a reference.
![20250131_193350](https://github.com/user-attachments/assets/e6278477-0ae2-4d13-85b9-9529d3a643a0)

Each BGA machine differs, and even the climate of where it is located is of important influence, and as such, your profile is specific to your own setup.
A very good BGA machine may be able to accurately control its output to match the temperatures requested in the profile, but for simply removing the CPU, this is not utterly important.
![20250131_193423](https://github.com/user-attachments/assets/68ff106c-96fa-44e9-b347-8253d37b3904)

### Board support
To prevent warpage of the motherboard, ensure the board is properly supported along its edges and ideally also in the center. This will prevent board sag. Do not take this lightly!  

The machine illustrated below has 6 support pivots, and the bottom heater is positioned against the board, thereby supporting it nicely in the center.
![20250131_193336](https://github.com/user-attachments/assets/c6f39dfe-767b-408e-a000-eb1ae5fd21ea)

### Profile
What I prefer to do is heat the board using the IR plates, some heat from the bottom, and after a while as the board has heated up, the top heater puts the temperature over the leaded solder melting edge.
By probing the edge of the CPU chip with tweezers you can find out when the balls have melted. At this point, stop your profile and quickly lift the chip. No need to strain the board further by letting the profile go on longer than necessary.
![20250131_193730 mp4_snapshot_00 03 430](https://github.com/user-attachments/assets/3a6e78dd-d393-4cdb-85ad-a7047ddff55f)

![20250131_193746 mp4_snapshot_00 08 864](https://github.com/user-attachments/assets/b964d677-6425-44df-9ae3-dfe26cf46507)

### Cooling
Let the board cool for ~10 minutes. While the board is warm, it is most prone to warping. Be patient!

# Interposer mounting
With the CPU removed, it's time to continue with the next step in which we solder the interposer onto the Xbox motherboard!

## BGA pads cleaning
First up: cleaning the BGA pads. Apply ample flux, then use a chisel or bevel tip on your iron to go over the BGA area. A lot of solder will stick to your iron. Give the iron a nudge above a waste bin to get rid of most of the excess solder.
![20250131_211420](https://github.com/user-attachments/assets/aebbd82d-cecb-4c74-aa2c-2952a9041fdb)

About 80% of the solder can be removed this way in mere seconds, which will save a lot on desoldering braid.
![20250131_211159](https://github.com/user-attachments/assets/08c5f116-613c-4078-8bdb-d38d770f024b)

Wipe up the remaining solder using desoldering braid. Do **not** exert force on the iron. If your wick won't move, either wait a while (5-10s) for the wick to really heat up, or use a higher temperature on the iron. 
Better yet: increase contact surface between iron and the wick. This is why spade-like tips like the one shown below are so effective for this purpose: they are able to really pump heat into the wick, and thereby the pads underneath, allowing for solder to be removed from many pads at once.
![20250131_211129](https://github.com/user-attachments/assets/6f23cb17-0417-42df-82ac-a5c1216b38a9)

Clean up with IPA and kimwipes. Inspect that all pads are nicely flattened.
![20250131_211030](https://github.com/user-attachments/assets/4dfb2d35-a291-406d-a5c0-edea5a5d255d)

## Tenting via's in BGA area
The next step is a little tedious and by some considered superfluous. Personally I believe the increased chance of success merits the 10 minutes spent on it.  

Using tweezers we apply UV curable solder mask on each of the via's which sit in between the BGA pads in the CPU area.
![20250131_211538](https://github.com/user-attachments/assets/fe7b8cf1-a161-42e4-bc39-a6cbcb6c035f)

After curing, the result should look as follows.
![20250131_212937](https://github.com/user-attachments/assets/148a6aff-1029-411a-8541-6746ec9c6eb4)
![20250131_213042](https://github.com/user-attachments/assets/eae9d59b-38c9-4462-91e3-d5c35b3edfc6)

### Why tent the vias?
The solder mask on these 25 year old boards is not of incredible quality, so solder easily attaches to the via's if they are not tented as suggested.
Should the interposer move during reflow, it is very likely to cause a solder bridge to develop between a chip BGA pad and PCB via.
This has prevented many of my initial attempts to fail, leading to a point where I went to obtain x-ray images of the BGA area. These reveal the bridges formed between via and BGA pad, leading to a failed install.  

![x2 png 17f4e4579669279c0a5acf65a6f2d83d](https://github.com/user-attachments/assets/cce4e7f1-c5a5-4c50-9102-0c511fa1224a)  
 ![x1 png dea90d838c6f8d1b79eb490e8c339e8e](https://github.com/user-attachments/assets/e073a4b8-19d4-4e28-9ca9-4c42e8b746a8)  

Since these via's are located in between the 1.27mm pitch of the balls, the alignment needs to be good at about <0.15mm for this not to happen.

Note that at first I did not come up with the techniques where an interposer aligntool PCB is used and the interposer is secured firmly in place. As such, aligning the interposer accurately was *very* difficult.
With the improved technique, we can place the interposer dead accurately and thereby reduce likeliness of this phenomenom occurring. As such, it may be fine to omit this step. That said, for the first few upgrades one performs, definitely do not skip it.

## Positioning the aligntool PCB
In order to solder the interposer, we must accurately place it on the BGA pads. The technique described here makes use of an aligntool PCB.
This PCB is manufactured with the exact same dimensions as the actual interposer, and has 0.9mm drill holes going right through where the BGA pads are found on the actual interposer. 
This allows as it were to *see through* the interposer, enabling accurate positioning on top of the BGA pads on the Xbox motherboard. 

Solder 4 resistors of size 0603 on the underside of the aligntool. This way it is elevated to the same height at the components on the Xbox motherboard, thereby eliminating tilt.
![20250131_214745](https://github.com/user-attachments/assets/da9c4172-9c09-4f3f-b13a-b763930f51ad)

Next align it so that the holes cover the centers of the BGA pads, and then tape it in place.
![20250131_214156](https://github.com/user-attachments/assets/0f8fca0d-4f79-408e-b9fd-2a7f2ff566b8)

We'll now solder some (bulky) SMD capacitors along the edges of the aligntool PCB. Either attach them to surrounding passives, or scrape away some solder mask to reveal some copper to which the capacitors can attach with solder.
![20250131_214339](https://github.com/user-attachments/assets/3fea352e-0d6d-4eaa-b479-9ba40a17c442)
 
Suggested locations for the 1.6 revision are shown below.
![20250131_214700](https://github.com/user-attachments/assets/3b03c1c1-0c38-4238-841d-53e929ea98e4)

TODO: add picture with suggested capacitor locations for non-1.6 boards.

> Note: It's best not to completely box in the aligntool, but allow for some very minor play. Manufacturing tolerances may result in slightly different outlines between aligntool and interposer. During soldering, the interposer will settle in place correctly.

## Interposer preparation
Specifically of note: tack balls using thin layer of flux + very low air speed. Once attached, use (much) more flux and high air speed. Make balls look shiny. Clean with IPA.
TODO: elaborate further.
![20250131_215003](https://github.com/user-attachments/assets/53523f33-e50f-41f6-83f9-d19e86d7bca9)

## Soldering the interposer
Remove the tape from the aligntool and verify that it placing it in between the capacitors along its edge positions the PCB properly. If so, it's time to solder the interposer.   
Apply a small layer of flux on the BGA pads and use a brush or your finger (wear gloves, e.g. nitrile) to distribute a very thin layer. Note that more flux is not benficial: it increases likeliness for balls to travel during reflow.
![20250131_214831](https://github.com/user-attachments/assets/de0e4886-6f03-4abe-9c72-56dbc6509fe7)
![20250131_214911](https://github.com/user-attachments/assets/970ffb86-235d-4e0b-9222-2814b1a137ce)

Then place the interposer and head over to the BGA station.
![20250131_221401](https://github.com/user-attachments/assets/c90a45d2-483b-4772-ba08-c42565e4568e)

### BGA profile
Shown below is the BGA machine profile I use for the interposer. Again, this may not apply directly to your situation. Adapt as necessary.
![20250131_215757](https://github.com/user-attachments/assets/90e9f654-5921-4bcd-b42d-c3198f4b4db3)

The main idea here is to have the board temperature attempt to follow the recommended reflow profile for the (Amtech) flux that I am using. Additionally, it contains some controlled cooldown (4th through 6th column of the profile).
![firefox_tVtUtnWohH](https://github.com/user-attachments/assets/630051cd-01e5-4f31-a8f8-f8038aa88f35)

After the profile finishes, allow the board to cool down for about 10 minutes before continuing to work on it.

## Intermediate checks
At this point clearly the Xbox cannot boot, but there are a few things we should verify to ensure we're good to carry on.
Briefly remove the GPU heat shielding tape from both sides of the board before performing these measurements.

On the interposer, measure the following using a digital multimeter:
 - VCORE --> reading should start at ~50 ohms, then continues to rise indefinitely
 - VREF  --> ~75 ohms stable
 - VTT   --> ~50 ohms stable
![pcbnew_oaYOb1aO3B](https://github.com/user-attachments/assets/d166882a-c723-43b4-b1d5-f4e9757d27ca)

If any of these read differently, the interposer is incorrectly aligned or a bridge has formed underneath it. It is then **pointless to continue**.  
Remove the interposer and start fresh. In this case I always recommend return to stock state, with the original CPU.

The next check is for the voltage rail powering the MCPX and XGPU:  
 - VGPU: ~20 ohms, slowly rising -- measures 1.75V when powered on.
Must be AT LEAST 2.5 ohms. If it reads <1 ohm the board has warped and a bridge has formed under the XGPU, or the XGPU has died from the heat. In most cases the board cannot be resurrected without transplanting or reballing the XGPU.

TODO: picture of where to measure this on the board revisions.


Finally, if these checks pass, turn on the Xbox. just the AV cord, PSU and front panel need to be connected.  

We expect the Xbox to FRAG. Other outcomes: 
 - If the Xbox does not turn on: probably a short that needs to be resolved. Remove interposer and start over.
 - If front LED blinks orange and fans turn on at 100%: likely a bridge on some of the address lines. Remove interposer and start over.

Put the aluminum tape back before continuing with the next steps.

## Populating the interposer
Unless you obtained a prepopulated interposer, solder the components from the [BOM](https://htmlpreview.github.io/?https://raw.githubusercontent.com/zzattack/xbox-cpu-interposer/main/kicad/bom/ibom.html) onto the interposer now.
These are simple resistors and capacitors and should form no challenge if you're tackling a procedure like this.

# Soldering the CPU
We've arrived at the final step of the procedure: soldering the actual CPU.  

For some background info: the CPU sits on top of the interposer. While soldering the CPU, the do not wish to reflow the BGA balls which attach the interposer to the Xbox motherboard. To achieve this, we use a *Bismuth* soldering paste with lower melting temperature (138°C) than the leaded balls (183°C).
I personally like to use TS391LT from CHIPQUICK for this. The purple needle head works nicely for distributing a correct amount of paste pneumatically, but dispensing by hand is completely viable too.
![20250131_221951](https://github.com/user-attachments/assets/c2316fad-7e2b-4a51-81e3-db82656d94bd)

Pneumatic dispenser with foot pedal and timed bursts allows for placing the 370 solder paste blobs in about 5 minutes.
![20250131_222217](https://github.com/user-attachments/assets/ef86345c-0bce-4453-8bda-7c8c594e6b50)
![20250131_222928](https://github.com/user-attachments/assets/a32eb8df-8720-4f56-bb8f-f60631e7cd2d)

Now place your CPU centered in the blobs. Try to be as accurately as possible when initially setting it down. If adjustments are needed, lift the CPU slightly instead of shoving while the pins still make contact with the interposer. 

Make sure alignment is good before placing the board onto your BGA machine.
![20250131_223116](https://github.com/user-attachments/assets/6067f519-0566-4e90-9769-765a3180b6a9)

## BGA profile
Starting point for the BGA profile for the CPU with Bi57 paste:
![20250131_223323](https://github.com/user-attachments/assets/341adf83-c0dc-466a-9c9c-015c3cade21e)

Again, adapt to your situation. When the paste melts, the effect of the paste *cuddling* up onto the CPU pins is quite pleasing to watch.

I like to use a 60x60mm nozzle which is able to get all the pins to melting temperature roughly at the same time.
![20250131_223353](https://github.com/user-attachments/assets/79eec532-39ce-46b6-b997-9c071b35e71e)

Again, wait about 10 minutes after the profile completes before handling the board so as to not unnecessarily stress it or induce potential warping.

## Testing
At this point, the Xbox should boot! Inspect the pins to ensure all paste has melted and no bridges have formed. Remove the GPU heat shielding tape once more.
![20250131_224609](https://github.com/user-attachments/assets/0a7134a7-b863-410a-9c84-923ac091cde4)

If so, power it on and keep your fingers crossed.  If you get a boot logo, turn off the Xbox. The CPU is still operating at 1.70V but it's intended for only 1.45V, so we'll address that next.
![20250131_225238](https://github.com/user-attachments/assets/ad402328-bc5c-44a1-921f-5881708fc5ff)

If the xbox boots, congratulations, you have performed potentially one of the toughest console mods out there.  

### Troubleshooting
If it does not boot, unfortunately, not a lot of diagnosis other than what was mentioned in the _Intermediate checks_ section is possible. A thermal cam could reveal potential shorts.
It's also quite possible that some of the balls simply did not make proper contact. Do not give up. Most people needed many attempts (>10 for some!) to record their first success.
Some general tips:
 - Work cleanly. Use isopropyl alcohol after every step involving flux.
 - Take your time, work patiently. This is a large effort and is often too much work to run in one sitting.
 - Refer to this guide constantly. Do not skip steps. Double/triple check your work.
 - If anything feels like it could be improved, do so right away. That's always less work than restarting from scratch.
 - Babysit the BGA profiles at first:
   - Watch closely for board warp.
   - Use a temperature probe taped to the side of the original CPU to get a feel for board temperature.
   - Adjust the profiles if they heat up too much, too fast, or not enough.


# Setting CPU VCORE
TODO. Refer to ACE github.
https://github.com/ACE-AU/OGX-PIII-CPU-VCORE-SETTINGS

# CPU/GPU heatsink bracket.
TODO. Refer to ACE github.
https://github.com/ACE-AU/OG-Xbox-CPU-GPU-Heatsink-brackets-for-Franks-Interposer
