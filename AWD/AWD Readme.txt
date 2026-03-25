Modified right front tensioner to accept an additional X stepper instead of an idler pulley.

Modified back X stepper mount to sit flush to the frame when using the Dual Y mounts(These remove the metal bracket used by the original ender 5 Y axis mount)

Added mounts for dual Y steppers. (credit to https://www.thingiverse.com/thing:4591932)

Modified the kinematics file, for klipper, for hybrid corexy to duplicate the X steppers instead of mirror. This ensures that both X steppers always run the same direction.
The .py file should replace the hybrid_corexy.py in "~klipper/klippy/kinematics"