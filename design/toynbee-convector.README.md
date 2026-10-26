Toynbee Convector is the look of a tomorrow imagined in the golden age of pulp science magazines: warm newsprint, rocket-age type, and a few loud inks used with confidence. Lay every page on `paper`, set running text in `body` with `ink`, and reserve `rocket-red` for the one thing that must shout: the `masthead`, a primary button, the lead headline. Set `masthead`, `headline` and `label` in uppercase. Use `atomic-teal` for links, secondary actions, "on" states and the 2px solid focus ring. `ray-yellow` is a signal fill only, so put `ink` text on it and never use it as text on paper. Use `night-sky` for deep panels, with `paper` or `ray-yellow` on top. Draw rules and outlines in `brass`, keep corners square (`radius-none`) except `radius-sm` on buttons and tags and `radius-round` on portholes, switches and badges, and space everything on the `space-24` grid. Flat ink only: no gradients, glows or soft shadows. The one shadow is `shadow-offset`, a hard ink offset, used on buttons and story cards. The voice is earnest, optimistic and a little breathless ("The Machine That Folded Tomorrow!"), uses "you" when speaking to the reader, and never uses emoji. All three faces are free on Google Fonts, and `components/bundle.css` imports them. Outside the bundle, load `https://fonts.googleapis.com/css2?family=Big+Shoulders+Display:wght@700;800;900&family=Old+Standard+TT:ital,wght@0,400;0,700;1,400&family=Courier+Prime:wght@400;700&display=swap`.

## Iconography

There are two registers, and both use the same 24 names: rocket, ray-gun, atom, saucer, planet, robot, helmet, starburst, comet, broadcast, dial, hourglass, telescope, bolt, moon, globe, airship, scissors, jetpack, flying-car, monorail, vacuum-tube, tesla-coil, dome-city.

- **Spot art** (`Spot`, and the SVGs in the Icons group) is the illustration voice: one clear silhouette per piece in a 2px ink keyline, flat colour from the palette, a single paper glint, and one accent (a twinkle, or two or three motion lines). Use it at 48px and up, on `paper` or `paper-deep`, one piece per card or panel. On `night-sky`, set it on a `badge`.
- **Line icons** (`Icon`) are the interface voice: 24px, 2px round-cap strokes in `currentColor`, beside Courier Prime labels at 14–18px, at 16–32px.
- Draw new pieces with restraint: a 64px grid with art inside 5–59; a 2px keyline outside and 1.25px lines inside; two or three inks plus paper; at least 2px of air between separate parts; halftone at most once, and only where it explains form (the shaded side of a rocket or planet); one accent, never several. If two parts blur together at 48px, cut one. No faces on anything but the robot, no real brands or characters, no emoji. The rocket always points up and away.

## Components

- **Actions:** `Button` (`primary` once per view, `secondary`, `signal` for offers, `night`) and `LeverSwitch` for settings that apply at once.
- **Labels:** `Tag` for categories and state, and `Starburst` for the single loudest offer in a view.
- **Foundations:** `Icon` and `Spot` (above).
- **Content:** `StoryCard` for teasers (with `spot` art), `Coupon` for the one sign-up per page, and `Transmission` for live messages and logs.
- **Instruments:** `Gauge` for a value against a redline, and `Chronometer` for years, clocks and counters.
- Every component reads its colours, type and spacing from tokens. Don't restyle one with literal values; if a variant is missing, add it to the bundle.

## Layouts

- **IssueCover:** masthead band, art panel, price burst, cover lines.
- **StorySpread:** headline stack, figure, two columns with a drop cap and pull quote, a 264px sidebar.
- **ControlPanel:** an app console on a 12-column grid, where controls drive instruments and status arrives as Transmissions.
- Pages have 48px margins and `space-24` gutters. Frame panels with a 2px `ink` rule and head them with a `label` over a 1px `brass` rule.

## Motion

Motion is mechanical, never floaty: needles swing with a small overshoot, switch knobs snap, flap tiles flip, the teletype cursor blinks, and buttons press flat. Keep it under 0.7s. Every animation stops under `prefers-reduced-motion`.
