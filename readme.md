# ovos-PHAL-plugin - DisplayManager IPC

Legacy implementation for mark1 faceplate, introduces yet another definition of "active skill"

This has been removed from ovos-core and is provided standalone for backwards compatibility


##  DisplayManager

DisplayManager module provides basic "state" for the visual representation associated with a Mycroft instance.  
The current states are:
   ActiveSkill - The skill that last interacted with the display via the
                 Enclosure API.

Currently, a wakeword sets the ActiveSkill to "wakeword", which will auto clear after 10 seconds.

A skill is set to Active when it matches an intent, outputs audio, or changes the display via the EnclosureAPI()

A skill is automatically cleared from Active two seconds after audio output is spoken, or 2 seconds after resetting the display.

So it is common to have '' as the active skill.

This version has been updated to also account for the mycroft-gui active skill