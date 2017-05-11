# Anki MCT (Massive-Context Cloze-Highlighted Text)
Based on the AJATT MCD (Massive-Context Clozed Deletion) concept. An MCT is essentially the same as an MCD, but the clozes are not a classical clozed deletion.

Rather, the generated cards shows/highlights the content (normally a word) being tested.
It would be the equivalent to setting the hint text of a cloze to the content that would otherwise be hidden.
This is much better for those with minimal vocabulary. I prefer it because it feels less like a test.
Adds to the fun-factor.
 
## Personal Setup

### My general process is as such.

1. Watch anime, read manga, and other general immersion activities.
1. When a sentence or passage grabs me, capture that context in a video, image, sound, and/or description.
1. Add as much of that content (text and context) as I feel confident with to the front side of a card. This might only be one word in the worst case.
1. Cloze the words I feel most confident in grading myself on.
1. Add as much of a translation, including readings for relevant words, as I feel confident with to the answer side.

### My Sentence deck is set up as such.

1. My custom card is based on Cloze so that it can support multiple clozes.
1. Fields are `Sentence`, `Context`, `Meaning`, `Extra`. Technically, the first two could be combined and the last two could be combined; this merely reflects personal preference.
1. `Sentence` and `Meaning` are question/answer counterparts.
1. `Context` typically contains a video, image, and/or description of the context to remind me what the sentence is from.
1. `Extra` typically contains readings and basic definitions.

## Goals

This addon only serves to provide some slight automation for this process.

This addon is intended to assist in generating card content in a platform independent way.

## Behaviour

Here's how this will work.

1. Cards with the MCT tag will be affected
1. Affected cards must at least have a front side with one or more of the field names (`Sentence`, `Text`, `Front`)
1. Affected cards must at least have a front side with one of more of the field names (`Meaning`, `Extra`, `Back`)
1. When affected fields lose unfocus, clozes will have their hint text set to their clozed text (i.e. `{{c1::text::text}}`)
1. Affected cards will automatically have some javascript added to the end of their HTML. These simply remove `[]` from cloze elements so they may be highlighted. It might also do some work to make user-scripting more convenient.

Some possible automations.

1. Back side is modified to add an outline for words/definitions by adding `ClozeText = ` for each cloze. It'd be even better to automate wrapping the `ClozeText` part with a search engine link (such as http://jisho.org) so the user may easily add extra details later.
1. Automate adding a search engine link for the text. Maybe back side only?
1. Add customization for search engines, text colors, etc.
