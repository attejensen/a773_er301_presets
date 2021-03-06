# Presets
All presets (should be) compatible with latest firmware  
Discussion thread: https://forum.orthogonaldevices.com/t/a773-presets-unit-files

Loading in the ER-301 (without having to worry about which unit was
used as container):
1) press “insert”
1) press S3 again (“Presets”)
1) browse to the file
1) press “enter” to load

##### Synth building blocks
* [ad](#ad) - AD envelope
* [ad exp](#ad_exp) - Exponential AD envelope
* [ad exp var](#ad_exp_var) - AD envelope with variable exponential response
* [decay env](#decay_env) - Decay envelope
* [glitch osc](#glitch_osc) - Glitchy, circuit bend style oscillator
* [rce sine](rce) - Simple recombination engine (sine genes)
* [rce tri](rce) - Simple recombination engine (triangle genes)
* [sloth](#sloth) - Slow random/chaos
* [stepped random](#stepped_random)
* [stepped random x6](#stepped_random_x6) - 6x stepped random

##### Voices
* [2op-fm](#2op-fm) - Two operator fm voice
* [bass pluck](#bass_pluck) - Simple plucky bass voice
* [karplus](#karplus) - Karplus strong voice

##### Drums
* [bd1](#bd1) - Decent kick drum
* [bd2](#bd2) - Better kick drum


##### Trigger/gate
* [gated burst](#gates_burst)
* [gate to trigger](#gate_to_trigger)

##### Audio mangling
* [buffer player](#buffer_player)
* [stutter](#stutter)

##### Effects
* [cheap reverb 1](#cheap_reverb_1)
* [cheap reverb 2](#cheap_reverb_2)
* [cheap reverb 3](#cheap_reverb_3)
* [cheap reverb 4](#cheap_reverb_4)
* [mono to stereo 1](#mono_to_stereo_1)
* [mono to stereo 2](#mono_to_stereo_2)
* [poor mans reverb 1](#poor_mans_reverb_1)
* [poor mans reverb 2](#poor_mans_reverb_2)
* [tuned resample](#tuned_resample)


## Synth building blocks
### ad <a name="ad"></a>
AD envelope with variable attack and decay, works with short triggers as input.  
Unit type: custom-unit  
CPU: 3.3%  
Controls:
* attack (0-5s)
* decay (0-5s)


### ad exp <a name="ad_exp"></a>
AD envelope (exponential response) with variable attack and decay, works with short triggers as input.  
Unit type: custom-unit  
CPU: 4.8%  
Controls:
* attack (0-5s)
* decay (0-5s)

### ad exp var<a name="ad_exp_var"></a>
AD envelope (variable exponential response) with variable attack and decay, works with short triggers as input.  
Unit type: custom-unit  
CPU: 5.6%  
Controls:
* attack (0-5s)
* decay (0-5s)
* exp (0-1)


### decay env<a name="decay_env"></a>
Very cheap decay envelope with exponential decay. This is just a slew-limiter with feedback (no fancy GUI) to keep it cheap. Adjusting time, might require adjusting the negative gain on the feedback. A bit unstable in a charming way.  
Unit type: slew-limiter  
CPU: 0.24%  
Controls:
* time: 3ms-786.32s


### glitch osc<a name="glitch_osc"></a>
Glitchy, circuit bend style oscillator  
Unit type: Custom Source  
CPU: 4.6%
Controls:
* v/oct  
* gate (silent when gate low)
* center (0-1)
* width (0-1)
* fade (0-1)

### rce<a name="rce"></a>
Simple implementation of a [recombination engine](http://www.futuresoundsystems.co.uk/returnosc2.html). One version with triangle "DNA" the other with sine. 
Unit-type: Custom source  
CPU: 7%
Controls:
* scissor (v/oct)
* center (-1 .. +1)
* width (0-1)
* fade (0-1)
* positive (v/oct)
* positive offset (-0.5 .. +0.5)
* negative (v/oct)
* negative offset (-0.5 .. +0.5)

### sloth<a name="sloth"></a>
Inspired by the non-linear circuits
[sloth chaos](http://nonlinearcircuits.blogspot.com/2014/09/sloth-chaos.html)
eurorack module.  
Unit-type: Custom Source  
CPU: 3.84%  
Controls:
* slowness: (0-1)

### stepped random<a name="stepped_random"></a>
Generte random value on trigger.  
Unit type: Custom Source  
CPU: 0.9%  
Controls:
* trigger


### stepped random x6<a name="stepped_random_x6"></a>
6x stepped random in one. One random value is the actual output, the
others can be reached inside the unit as rand1-5. Advantages over
stepped random is: 
1) a bit lighter on the CPU pr random (0.78% vs 0.9% for stepped random)
1) convenient if you need lots of random  

Unit type: Custom Source  
CPU:4.7%  
Controls:
* trigger




## Voices
### 2op-fm<a name="2op-fm"></a>
[![2op-fm demo on instagram](https://www.dropbox.com/s/x4j22gshjoptobn/2op-fm.png?raw=1)](https://www.instagram.com/p/BzLa0WuBjBB)  
Percussive FM voice inspired by [the 2opfm module by Super Synthesis](https://www.supersynthesis.com/products/2opfm?variant=3710980620328)  
Unit type: mixer-channel  
CPU: 8.4%  
Controls:
* v/oct
* ratio (0-1)
* index (0-20)
* release (0-1s)
* gate

### bass pluck<a name="bass_pluck"></a>
Simple plucky bass voice.  
Unit type: mixer-channel  
CPU: 8.4%  
Controls:
* v/oct
* trigger
* release (0-6s)
* feedback (0-1)


### karplus<a name="karplus"></a>
Karplus strong voice.  
Unit type: mixer-channel  
CPU: 6.2%  
Controls:????
* v/oct
* trigger
* brightness (0-1)
* damping (0-1)


## Drums
### bd1<a name="bd1"></a>
No so versatile kick drum.  
Unit type: mixer-channel  
CPU: 8%  
Controls:
* amp rel (amplitude decay time)
* pitch amt (pitch amount)
* pitch rel (amplitude decay time)


### bd2<a name="bd2"></a>
Quite versatile kick drum, with lots of sweet spots.  
Unit type: mixer-channel  
CPU: 10%  
Controls:
* freq 0-1 (frequency env amount)
* decay 0-1s
* feedback 0-1




## Trigger/gate
### gated burst<a name="gated_burst"></a>
![gated burst screenshot](https://www.dropbox.com/s/vmn27169oup4s3s/gated_burst.png?raw=1)  
Emits bursts while receiving a gate. The bursts are pulses with intervals of "burst time" and length "burst time/2".  
Unit type: custom-unit  
Controls:
* burst time: 0-1000 ms  


### gate to trigger<a name="gate_to_trigger"></a>
![gate to trigger screenshot](https://www.dropbox.com/s/jf2uykexkvd0rv1/gate_to_trigger.png?raw=1)  
Converts incomming gates to triggers of selected length.  
Unit type: custom-unit  
Controls:
* trigger time (1-1000ms)


## Audio mangling
### buffer player<a name="buffer_player"></a>
Grabs audio and play it pitched.  
Unit type: two-bands  
Controls:
* v/oct
* grab
* dry/wet

### granulator 1<a name="granulator 1"></a>
Plays loaded sample in granular bursts  
Unit type: manual grains  
CPU: 9.2%
Controls  :
* play trigger
* range (0-1)


### granulator 2<a name="granulator 2"></a>
Mangles incomming audio and plays it in granular bursts  
Unit type: custom effect  
CPU: 17.8%
Controls  :
* play trigger
* range (0-1)

### stutter<a name="stutter"></a>
Repeats snip of audio on gate high.  
Unit type: Custom Effect  
CPU: 7.0%  
Controls:
* clock
* gate
* mult
* div


## Effects
### cheap reverb 1 + 2<a name="cheap_reverb_1"></a><a name="cheap_reverb_2"></a>
[![Cheap reverb demo on instagram](https://www.dropbox.com/s/rmiqyzhux5fnle1/cheap_reverb.jpg?raw=1)](https://www.instagram.com/p/BxetV5FhZKT)  
Unit type: six-bands  
CPU usage: 7.2%  
Room size reverb that doesn't tax the CPU. Works on stereo channel, but is mono in, mono out.  
Controls:
* size (0-1)

### cheap reverb 3<a name="cheap_reverb_3"></a>
Unit type: Custom Effect  
CPU usage: 3.25%  
Wonky delay based reverb, very light on the CPU.  
Controls:
* wet (0-1)

### cheap reverb 4<a name="cheap_reverb_4"></a>
Unit type: Delay 
CPU usage: 1%  
Wonky delay based reverb, extremely light on the CPU.  
Controls:
* delay (0-1000ms)
* fdbk (0-1)
* wet (0-1)

### mono to stereo 2<a name="mono_to_stereo_2"></a>
More sophisticated (using comb filters), better mono compatibility, but more
expensive on the CPU.  
Unit type: two-bands  
CPU (on stereo channel): 18%  
Controls:
* width (0-1)
* depth (0-1)


### poor mans reverb 1<a name="poor_mans_reverb_1"></a>
[![Poor mans reverb demo on instagram](https://www.dropbox.com/s/lnljtk90a9yrt26/poor_mans_reverb_1.jpg?raw=1)](https://www.instagram.com/p/BvUDRwlF5Ic)  
Granular reverb based on [Neil Parfitts reverb idea](https://www.youtube.com/watch?v=swXpnqot4-Q), recording with a Dub Looper, with dub controlled by incoming signal.  
Unit type: two-bands  
CPU: ~24%  
Controls:
* sense
* length (10ms-1s): length of grains
* speed (10-500Hz): speed of grains
* scrub (0-1): random scrubbing of playhead
* dry (0-1)
* wet (0-1)


### poor mans reverb 2<a name="poor_mans_reverb_1"></a>
Variation of [poor mans reverb 1](#poor_mans_reverb_1), but recording with a Feedback Looper for a different flavor.  
Unit type: two-bands  
CPU: ~16%  
Controls:
* length (0-1s): length of grains
* speed (10-500Hz): speed of grains
* v/oct: pitch of reverb
* dry (0-1)
* wet (0-1)


### tuned resample<a name="tuned_resample"></a>
Sample rate reduction, with pitch tracking.  
Unit type: Two Bands  
CPU: 4%  
Controls:
* v/oct
* offset in v/oct
* dry/wet (0-1)
