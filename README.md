## Investigations

- For live region, we cannot use `disabled` attribute for `<button>`
   - We can consider `onFocus` and then blur
- For live region, we put `<select>` plus multiple `<option>`. Windows Narrator just said, "Please select a location, combobox, collapsed, has popup." It does not say number of choices nor its content
   - We might not need to put every `<option>` inside, just the placeholder (a.k.a. current selected), but we need to verify with other screen readers if the narrated sentence is what we expected
      - If we need to put all `<option>` because other screen readers read its content, are there any `aria-xxx` substitutes for the just number of items inside? So we don't render everything isnde.
   - Android
      - With `<select><option>Please select a location</option></select>`, TalkBack do not narrate the whole `<select>`, the user doesn't really know it's there
      - With `<select aria-label="Please select a location"></select>`, TalkBack said, "Please select a location", but no indication of "dropdown, collapsed, has popup".
