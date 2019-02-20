# Propositions for editable window for reaticulate

So mainly, the script just write stuff it gets from fields into the
Reaticulate.reabank file

It works in 4 steps gradualy (even if steps 3 and 4 could be enable together),
from left to right.

## 1st step

On the left panel, clicking the add button should open a box where we could enter
- the group (g option in the actual script). could be divide in 2 fields as you mentioned in your documentation vendor / product.
- the name (n option in the script)
- A comment (m option in the script)
- bank number
- program number
- bank name

Closing this pop-up window write an empty entry in the script
with those options for example :

```
//! g="Orchestral Tools/Berlin Strings" n="V1"
//! m="Using custom keyswitch (24 to 35)"
Bank 1 1 OT-BS - V1
```

if no selection on the left panel, others panels are not usable

"del" button delete selected entry
"clone" button is the clone function

## 2nd step
Once done, we could go to the center panel by selecting
the new entry we just created in the left panel (or an already existing one)

As shown in the schema, yellow is the selected slot we are working on, grey are the other slots

Center panel is now editable but NOT the right panel

clicking the add button in the center panel creates an editable line below (or a popup window again)
with a mix of editable fields and drop-down options.

- articulation name (if we take the example below here will be "Sustain lmm Romantic vibrato - C1")
- icon (i option) a drop-down list ?
- color (c option) a drop-down list too or an hexa code color #RRGGBB ?
- Program number (in the example below it's 20) drop-down list !

```
//! c=legato i=note-whole 
20 Sustain lmm Romantic vibrato - C1
```

## 3rd step

Now, we can select the slot we just created in the center panel and it makes the right panel editable.
And here we can provide options for the "o" option of reaticule.

It could be
- type ( drop-down with Program & CC & Note & Note-hold & art)
- value 1 or DATA 1 for the previous selected type (C-0 if type=note OR 32 if type = CC, etc...)
- value 2 or DATA 2 (could be a velocity value or range)
- channel
- group

If I take your example and apply to the picture the "o" parameters:
> "This one from Cinematic Studio Strings sends 3 separate notes at specific velocities
> to set sordino and legato in addition to the sustains patch.
> //! c=long-light i=con-sord o=note:12/note:22,1/note:23,127
>7 con sordino"

- group number (drop down 1 to 4, 1 selected by default)


## 4th step
Extra options for the selected articulation in center panel
- "f" option
- "n" option 

## options not covered
- the "off" option
- the "chase" option for banks


## Improvement
- each slot column head could be clickable to sort articulation
- if method is keyswitch, the keyswitch value is displayed in the articulation window
