# Fusion 360 postprocessor file for techno Router in ITP

Original file was download on Aug 18,2017 from http://cam.autodesk.com/posts/?p=techno_cnc_router#

The only problem with that postprocessor file is it will drag tool at 0 height after a tool change, leaving a tool mark at rapid speed. So this may both damage part and bit.

I figured out it was caused by "G79 Z0.", which will retract tool to 0 height. In most cases, 0 is not our retract plane.

So I edited post processor and changed it to 0.5 and it can solve the problem. If your 0 plane is lower than stock up surface or your bed is not even. Try to edit G79 in NC file manually.

Here is photo before and after edit. This photo was taken when G79 was set to 0.1

![](https://raw.githubusercontent.com/DeqingSun/technoCNC_ITP_postprocessor_Fusion/master/toolMark.jpg)

If 0.5 retract distance is enough for you, no further editing is needed. Just use post processor in this repo.
