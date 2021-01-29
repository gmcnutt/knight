29 January 2021
------------------------------------------------------------------------------

Trying to figure out how to make the walk animation look natural
without any sliding or slipping on the ground. There are 10 frames in
a walk cycle. When I lay the frames out as a time sequence the head
advances 36 pixels in the first half, so that would be 72 pixels per
cycle. At 10 frames per second that would be 72 pixels per
second. That is very close to what I experimentally determined looks
best.

I still sense some slippage taking place, probably because the frames
do not advance perfectly. Also, maybe more importantly, the update
method which increments the speed is not perfectly timed with the
animation frame rate, so the same frame would appear to slide over
several updates as the image moves but the frame does not advance. To
make it look perfectly smooth I'd need to coordinate the movement
distance with the frame advance. That seems to run counter to what the
phaser 3 framework is designed to do. You set the velocity of a sprite
and the frame rate on the animation and the framework does the
rest. As the frame rate increases the illusion improves.

28 January 2021
------------------------------------------------------------------------------

Added a basic walk-cycle animation based on the phaser 3 tutorial from
their main site. The animation was copied by hand from page 25 of
*Animation by Preston Blair*.

Added a ground sprite. The player appears to be walking a few pixels
above it because there are some grass blades sticking up, and the
player walks on the upper ground image border. The ground should be
flat, then, and any grass or vegetation should be on a background
sprite.
