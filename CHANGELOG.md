# Changelog

All notable changes to **Exactly** are recorded here.
The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and version numbers follow [Semantic Versioning](https://semver.org/).

- **Major** (2.0.0): a big redesign or a change that breaks how people use it
- **Minor** (1.1.0): new features or new content
- **Patch** (1.0.1): bug fixes only

## [Unreleased]

Ideas not built yet:
- Let people add their own categories, brand names and palettes
- A "share this challenge" link
- A difficulty setting (for example a time limit or a 3-colour mode)

## [2.0.0] - 2026-11-17

A full redesign. The old-computer window with three scrolling lists is replaced by a pink Y2K "media player" with three card decks.

### Added
- **Card decks.** Category, Brand Name and Palette are three decks. **Deal** (the round play button or the Space bar) throws the old cards aside, shuffles each deck, deals a new card face down and flips it over, one deck after another.
- **Pick**: a searchable list for each deck, to choose a card yourself.
- **Hold** now pins a card with a heart, and the button reads "♥ Held".
- **Recent Rolls** panel, styled like a playlist. It shows the last 12 challenges with mini palette swatches, numbered with the roll count. Click one to bring it back.
- **How to Play** panel, switched with Recent Rolls using the tabs beside the cards.
- **Click a colour to copy its code.** The label flashes "Copied!" and a message confirms which code was copied.
- Colour codes now show the `#` (for example `#C97B57`).
- A status line under the cards ("Now dealing: …") with a roll counter.
- A pink taskbar with a live clock and an **aismbx github** tab linking to https://github.com/aismbx.
- New fonts: **Urbane Rounded** (Light, Medium, DemiBold and Bold, in the `fonts` folder) for all text, and Dancing Script (from Google Fonts) for the logo and card backs.
- A new favicon: a white heart on hot pink.

### Changed
- **New look:** a pink Y2K desktop and media-player window, glossy gel buttons, a dark plum card table and pink card backs. It's based on reference images of pink media-player skins and 2000s pink websites.
- **Visitors start with face-down cards** labelled Category, Brand Name and Palette, and "Press Deal to get your challenge." There's no pre-filled example any more.
- Category and brand name cards use the same font, colour treatment and size. The brand name is pink, and both are centred.
- On phones, cards become wide and stack, the side tabs become a row across the top, and the side panel sits under the cards.
- Recent rolls are saved under a new key (`exactly-deck-history`), so the history starts fresh after this update.

### Removed
- The three scrolling lists, the big pink heading and the old Windows-style window.
- The palette description text (for example "A traditional German, Dutch and Scandinavian sweet…"). It's still in the code, but it isn't shown.
- Tried during the redesign and taken out:
  - a menu bar (Deal, Release holds, Copy challenge, Help);
  - a "Now Dealing" tab;
  - the tagline on the brand name card;
  - tapping a card to flip it over;
  - extra detail on the card backs.

### Fixed
These bugs were found and fixed while building 2.0.0:
- **Layout jumped when switching panels.** Recent Rolls and How to Play were different heights. The panel now always matches the card area and scrolls when the list is long.
- **Cards widened after the first deal on phones**, pushing the page down. The card area now keeps its width.
- **Long brand names broke mid-word** ("Smudg / e"). Words now only wrap between words.
- **Script brand names were hard to read** (for example "Brr"). The brand name now uses Urbane Rounded.
- **Category and brand name text sizes didn't match**, because short words were made bigger. Both now use one size.
- **The challenge box changed size when a colour was copied.** The "copied" message now floats over the box instead of sitting inside its layout. The backup copy method no longer nudges the page or moves focus.
- **The challenge box changed height between deals** as the sentence went from one line to two. It now reserves room for the longer sentence.
- **The minimise icon sat lower than the others** in the title bar. The window icons are now drawn shapes, centred in their buttons.
- **Joined words in the side tabs** ("NowDealing") on narrow screens.

## [1.4.0] - 2026-10-26

### Added
- GitHub Pages packaging: a standalone `index.html` with its own `<head>`, page description and favicon.
- `.nojekyll` file so GitHub Pages serves the site exactly as written.
- `README.md` with step-by-step upload instructions.
- This changelog.

### Fixed
- **Selected item scrolled out of view.** After Generate, each list scrolled to the wrong place, so the highlighted pick was often off-screen. The list now scrolls so the pick sits in the middle.
- **Missing spaces in the big heading.** Words ran together (for example "shop×Pearl") because the spaces between animated words were being dropped. Words now have proper spacing.
- **Last colour swatch cut off.** On narrower windows the fifth swatch was pushed past the edge of the palette panel. All five swatches now always fit.
- **Copy fallback copied the wrong text.** If the browser blocked clipboard access, the backup method always selected the challenge sentence, even when you clicked "Copy hex codes" or a single swatch. It now copies whatever you clicked. If that also fails, it shows the text on screen so you can copy it by hand.
- **History was stored under the old name.** Recent rolls were saved under the key `oddly-history`. They're now saved under `exactly-history`, and history saved under the old key is still read, so nobody loses their recent rolls.

## [1.3.0] - 2026-10-26

### Added
- 117 new categories, taking the total from 40 to **157**. They cover food and drink, pets, beauty, sport and leisure, services, culture, travel, tech, and home and shopping. Examples: Funeral Home, Kombucha, Detective Agency, Haunted House, Dating App.

## [1.2.0] - 2026-10-26

### Added
- 167 new brand names, taking the total from 45 to **212** (for example Pickle, Mavis, Hiccup, Ta-Da, Eventually).
- 68 new colour palettes, taking the total from 32 to **100**. Each one has a short description and 5 hand-picked colours (for example Burnt Toast, Petrol Puddle, Disco Ball, Penguin Enclosure).

### Checked
- No brand name or palette appears twice, and every palette has exactly 5 colours.

## [1.1.0] - 2026-10-26

### Changed
- Renamed the generator from "Oddly Specific" to **Exactly**. The new name appears in the browser tab, the window title bar and the status bar.
- The big pink heading no longer uses the old name. It now reads "design exactly this" when the page opens and "exactly." after you pick something yourself.

### Removed
- An unused list of heading words (`WORDS`) left over from the first version.

## [1.0.0] - 2026-10-26

### Added
- First release of the generator, modelled on the "Oddly Specific" design challenge video.
- A retro Windows-style window with three scrolling lists: **Category**, **Brand Name** and **Color Palette**.
- A **Generate** button that spins all three lists and slows each one to a stop on a random pick. The Space bar also generates.
- **Hold** checkboxes that keep a column's pick while the others spin.
- Click or use the arrow keys to choose any item yourself.
- A palette preview panel with the source's name, a one-line description and 5 colour swatches. Click a swatch to copy its hex code.
- A challenge card that writes the prompt as a sentence, with "Copy prompt" and "Copy hex codes" buttons.
- A **Recent rolls** list showing the last 8 challenges, saved in the browser.
- Starting content: 40 categories, 45 brand names and 32 colour palettes.
- Phone-friendly layout, and animations are turned off for people who ask for reduced motion.

[Unreleased]: #
[1.4.0]: #
[1.3.0]: #
[1.2.0]: #
[1.1.0]: #
[1.0.0]: #
