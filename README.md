The main reason for forking this:

A lot of VST plugins have now switched from VST2 to VST3 - some refuse to work with Pedalboard 
unless using an old version (Tonal Balance control, I am looking at you)

So it would be a huge advantage if the code could be converted to the newer format.

In my personal use I patch Pedalboard 2 into the windows sound path via VB Hifi Cable 
(a virtual patch cable that hosts a sound driver which can be used as default sound output). 
Then I have a main chain that hosts the following plugins:

=> YouLean loudness meter
=> Fabfilter Pro Q4 (to test / apply corrective moves when doing mix reviews) 
   => Tonal Balance Control 2  (izotope, to see why a mix sounds lacking, muddy, boomy or overhyped)
   => Fabfilter Pro-DS (for bad mixes)
      => bx_solo (plugin alliance, mainly to toggle MONO to check MONO compatibility)
         => ARC 3 (IK multimedia, room correction software)
            => Audio Output

This is a useful chain, that makes sure all my audio is calibrated correctly while listening to anything
including YouTube, Spotify or any creativee software that plays back sound. I only use the equalizer during 
mix reivews to test my hearing and see how a mix could be improved, when I hear a problem.


🛠 What Needs to Be Done
✅ Key Tasks:

 Update JUCE to latest version (or check if it’s compatible with current VST3 SDK)

 Create a new JUCE plugin target
      Type: Audio Processor
      Format: VST3
      
  Port UI from standalone app to plugin editor
      The GUI is modular, so may need reworking for plugin constraints (resizing, DPI)

  Handle plugin state saving / loading
      Serializing chains, parameter states
