# Fresco hero treatment

The supplied portrait fresco is preserved in `moodboards/fresco-study/source.jpeg` and `public/design-system/fresco-source.jpeg`.

The initial projects-page treatment enlarged that portrait to fill a landscape banner. The revised direction follows `sculpture-image-process.md`: a generated landscape reinterpretation, luminous painted figures on the right, dark image-derived umber negative space on the left, and a soft fade into the page background. This is illustrative artwork, not an unchanged or restored historical photograph.

## Built-in image generation prompt

Create a high-resolution landscape 1536x1024 website hero artwork. Input 1 controls content: reinterpret the weathered fresco with its recognizable three main figures, blue-robed kneeling man lower left of the group, terracotta-robed standing man reaching toward him, ochre-robed man behind him. Preserve painted fresco medium, gestures and aged plaster detail, improve crispness without converting to sculpture or modern photography. Input 2 controls atmosphere only: sculptural editorial hero with richly luminous warm pigment on the RIGHT, dark umber #302a25 negative space covering LEFT 45%, a smooth cinematic fade from darkness into the fresco. Compose all three faces inside the right 55% and comfortably within vertical 20%-70% for a wide banner crop. Retain fresco blue, terracotta, ochre and warm plaster highlights. Deep dark left background, tactile fine details in the figures, soft bottom fade to umber. Do not darken the entire picture: subjects should remain vivid and crisp. No typography, UI, borders, bounding boxes, collage panels, sculpture, new people or invented objects. This is one seamless background image.

Reference inputs: supplied fresco photograph and the user's Sculptural Editorial mood board. Editable face boxes must be refitted to the generated output rather than reusing original-photo coordinates. The original collection layout remains in place.

## Integrated assets

Generated artwork: `public/design-system/fresco-editorial-v2.png` (1536 × 1024). Original output retained under the Codex generated-images directory. Overlay: `public/design-system/fresco-editorial-overlay.svg`. Face boxes `(x, y, width, height)`: kneeling `(745,460,125,133)`, central `(1130,169,166,170)`, right `(1355,148,134,155)`. Umber corners are 2px, with a faint 1px perimeter. Both image layers use the original collection hero's matching desktop/mobile fit and crop. The CSS adds a restrained side gradient and a bottom fade to the page's umber background without washing out the figures.
