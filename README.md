# smashbox-eightbuttons-concept
A short JavaScript experiment demonstrating the possibility of using eight direction buttons on the Hitbox Smashbox

The [SmashBox controller][http://www.hitboxarcade.com/blogs/smash-box] by Hitbox Arcade is a new Gamecube controller
in testing that allows players to play Super Smash Bros. or similar games by using only arcade style buttons. In
addition to being more precise, the controller also promises to be far more ergonomic and not only allow players with
wrist disabilities to play Smash competitively, but also help players to prevent developing those wrist ailments
in the first place.

![SmashBox controller](http://cdn.shopify.com/s/files/1/0166/4408/files/SB1_grande.jpg?14858935408304031890)

Unfortunately, in its current state, it suffers from a particularly strange flaw: in order to input partial
analog angles, the Smashbox makes the player hold modifier buttons down in the controller's D-Pad area.
This, of course, appears [convoluted and nonintuitive to some users]
(https://www.reddit.com/r/smashbros/comments/4sryjb/why_the_smashbox_is_broken_at_a_fundamental_level/),
which is to be expected from any system that translates digital to analog. However, something more serious
is that the controller has been [banned](https://youtu.be/7KN0UvnTFBM?t=51s) at the Genesis 4 tournament
due to fears that allowing it will end up allowing any number of modified controllers into Smash, 
including controllers with macros - which the modifier buttons are not quite, but appear to be because
of the simple fact that inputting a different stick magnitude can completely change the action you
input.

This problem won't be completely solved without completely nerfing the controller and not allowing partial
inputs at all (which would make the controller disadvantageous in tournaments), but I got to thinking of
another possible system that could help solve both of these problems: what if, instead of four modulatable
analog buttons, we had _eight_ that represented the eight cardinal directions, and simply inputted the
_average_ analog direction of all buttons pressed?

For instance, if the player only presses NW, they will input the Control Stick going up-left as far as it
will go. However, if they press N and W, they will input the Control Stick going up-left to only about two
thirds of its normal magnitude (.5 instead of .707). Pressing SE as well will lessen the magnitude further,
and pressing S or SW will pull the angle closer to W. Essentially, to pull the stick in a particular direction,
the player holds that button.

(As to where the buttons will be placed, they would be placed in corners around the existing T-shape so that
the existing WASD configuration can still be used).

This repository simply generates the set of analog inputs that are possible with this input scheme and
displays them in an attractive format. The resulting picture is reproduced below:

![Results](results.png)

As you can see, this control scheme offers a terrific amount of possible analog inputs, with 72 in the
significant outer range and even more in the range closer to the origin. This not only exceeds the number
of possible inputs in the present Smashbox (as of December 2016) but also offers the benefit of not only
being somewhat more intuitive (when in doubt, press the button leaning into the tilt or release the button
leaning away) but also lessens the arbitrariness of the modulation, perhaps enough to where it would
no longer be conflated with a macro.

## Proposals for improving this experiment

- Allow users to hover over input points to see what buttons to press to get that result
- Add "common sense" detection - combinations requiring convoluted hand positions will be flagged or removed
- Allow users to configure how the average is calculated so that more angles can be feasibly inputted.
