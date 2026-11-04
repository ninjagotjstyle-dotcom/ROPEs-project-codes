# ROPEs Interactive Puzzle Chest

An Arduino-powered puzzle chest for a haunted-house or escape-room experience. Players follow clues, discover a code, and enter it on a keypad. The finished chest is planned to open its lid automatically after the correct answer.

**Stage:** Electronics prototype and mechanical planning  
**Last updated:** November 4, 2026  
**Update schedule:** Every Monday  
**Project goal:** Build, test, and document a working interactive chest, including at least 50 hours of project work.

## Progress so far

This is a cumulative starting record. Earlier work is grouped here because exact weekly dates have not all been recorded. Completed items reflect prototype tests; the full chest has not been assembled or tested.

### Built or confirmed

- [x] Tested the keypad with an Arduino Mega 2560.
- [x] Tested code entry and submission using `#`.
- [x] Added lock/unlock state tracking and LED feedback.
- [x] Tested changing the unlock code through keypad programming mode.
- [x] Tested a startup check that lights the green and red LEDs.
- [x] Tested the 16×2 LCD separately.
- [x] Tested an LED using the Elegoo breadboard power module and a battery.
- [x] Confirmed a teacher-approved project mentor.

### Planned or awaiting testing

- [ ] Reconnect the LCD to the working keypad prototype.
- [ ] Add and test Serial Monitor controls for programming permission.
- [ ] Verify that a changed unlock code survives a restart.
- [ ] Verify red LED feedback during a wrong-code attempt.
- [ ] Measure the existing box and linear actuator.
- [ ] Check the actuator label, power requirements, mounting, and ability to hold position.
- [ ] Select a suitable actuator driver and power supply.
- [ ] Add a front key switch for main power.
- [ ] Build and test the marble and invisible-ink clues.
- [ ] Assemble the chest and test the full player experience.

## Code and controls

The prototype currently uses a 4×4 keypad. A 3×4 replacement is being considered; its wiring and key map will need updating before use.

| Control or feature | Purpose | Status |
| --- | --- | --- |
| Number keys | Enter a code | Prototype tested |
| `#` | Submit the entry | Prototype tested |
| `*` | Clear the current entry | Recheck with the latest sketch |
| `**` | Start changing the unlock code | Prototype tested; permission control planned |
| Green and red LEDs | Show feedback | Startup check passed; wrong-code feedback needs rechecking |
| `PROGRAM ON` in Serial Monitor | Allow keypad code changes | Planned |
| `PROGRAM OFF` in Serial Monitor | Block code changes and cancel an unfinished change | Planned |
| Front key switch | Turn the chest on and off | Planned |

Programming permission should start **OFF** each time the Arduino starts. Players should still be able to enter answers while code changes are disabled.

### Recorded prototype connections

Check these against the latest sketch before reconnecting components.

| Component | Mega pins |
| --- | --- |
| Keypad rows | 22, 23, 24, 25 |
| Keypad columns | 26, 27, 28, 29 |
| Green LED | 30 |
| Red LED | 31 |

LCD connections and actuator controls will be documented once the final wiring is confirmed.

## Puzzle and lid plan

1. Players find colored marbles and a UV flashlight.
2. Invisible ink on a removable prop reveals a clue to the color order.
3. A decoder maps the colors to digits.
4. Players enter the resulting code on the keypad.
5. The Arduino gives feedback and, once the mechanism is built, commands the lid to open.

The current mechanical idea is a linear actuator attached between the box and lid. It would hold the lid closed and extend to open it. This is a proposal until its dimensions, holding ability, power requirements, and mounting are checked with the mentor.

## Weekly progress log

Entries are labeled by the Monday that starts the week. Every Monday, finish the previous week's entry with actual results, then add the next week above it. Keep older entries so the history stays visible.

Record only work actually completed. Put ideas and intended work under **Next steps**, and use **Not tested yet** when hardware was unavailable.

### Week of November 2–8, 2026 — In progress

**Completed**
- Created this README and a reusable Monday update format.
- Collected the known prototype results and remaining work into one record.

**Testing and results**
- No new hardware tests recorded in this entry yet.
- Box and actuator measurements are still pending.

**What I learned / decisions**
- Changing permission to program a code and actively entering a new code are separate states.
- The actuator specifications need checking before selecting its driver and power supply.

**Problems / questions**
- Will the existing actuator fit the box, lift the lid, and hold it closed without power?
- Does the current sketch save a changed code through a restart? This needs a test.

**Next steps**
- Measure the box and actuator and record its label details.
- Review the latest sketch and add operator controls.
- Reconnect the LCD, then test keypad feedback.
- Review the actuator plan with the mentor.

**Evidence:** Add photos, screenshots, test notes, or links after completing the work.  
**Time this week:** Not entered yet.  
**Total project time:** Not entered yet.

## Copy this template each Monday

Copy the Markdown inside this block into the weekly log above the previous entry. Replace the prompts with your own results.

```markdown
### Week of YYYY-MM-DD–YYYY-MM-DD — In progress / Complete

**Completed**
- What did I finish or change?
- Which code file or feature did I work on?

**Testing and results**
| Test | Expected result | Actual result |
| --- | --- | --- |
| Describe the test | What should happen | What happened, or Not tested yet |

**What I learned / decisions**
- Explain one thing I now understand and why it matters.

**Problems / questions**
- What did not work, and what did I try?

**Next steps**
- My priorities for the coming week.

**Evidence:** Add links to photos, screenshots, videos, or commits.  
**Time this week:** ___ hours  
**Total project time:** ___ / 50+ hours
```

## How I update this README

1. Every Monday, finish the previous week's log using actual work and test results.
2. Copy the template to the top of the weekly log and enter the new Monday-to-Sunday dates.
3. Update the checkboxes, controls table, and last-updated date when something changes.
4. Add evidence links and actual project hours.
5. Save the README with a clear commit message, such as `docs: weekly progress for 2026-11-09`.

Keep this file named **README.md** in the main folder of the code repository.
