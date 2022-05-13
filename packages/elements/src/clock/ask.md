# intro
screen reader doesn't stop to stay on clock when use ↓↑ navigation for change value.
aria-live doesn't work when it put inside spinbutton or spinbutton can't focus. So spinbutton must have tabindex="0" 


# Solution 1 Each segments still have tabindex=0
<ef-clock interactive role="group">
  <div part="segment hours shifted" role="spinbutton" tabindex="0"> <!-- solution is this div -->
    09
  </div>
  <div part="segment divider" aria-hidden="true">:</div>
  <div part="segment minutes" role="spinbutton" tabindex="0">
    01
  </div>
  <div role="status" aria-live="polite" aria-label="Time: 09:01"></div>
</ef-clock>

# Solution 2 wrap by div and let it be spinbutton
<ef-clock interactive role="group">
  <div id="container" tabindex="0" role="spinbutton"> <!-- solution is this div -->
    <div part="segment hours shifted">
      09
    </div>
    <div part="segment divider" aria-hidden="true">:</div>
    <div part="segment minutes">
      01
    </div>
  </div>
  <div role="status" aria-live="polite" aria-label="Time: 09:01"></div>
</ef-clock>

# Solution 3 (optional) let aria-live element to lightdom

# ISSUE



Note for me
host should be role="group"
- let aria-label work
- same as Timepicker
spinbutton only in segment
- ↓↑ navigation of screen reader ignore clock
aria-live inside spinbutton doesn't work
- so host can't be spinbutton
#### shortcut
generateSegmentTemplate
- is segment
firstUpdated
- has keydown