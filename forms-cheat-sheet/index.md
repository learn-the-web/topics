---
layout: cheatsheet
group: web-dev-2

groups:
  - title: 'Tags'
    items:
      - name: '`<form method="post" action="…">`'
        details:
          - 'Tag that wraps around all the form elements.'
          - '`action` points to where the data should be submitted.'
      - name: '`<fieldset>`'
        details:
          - 'Used to group elements together, like radio buttons.'
          - '*Must always have a legend.*'
      - name: '`<legend>`'
        details:
          - 'Adds a title to the fieldset.'
          - '*Must be inside a fieldset.*'
      - name: '`<button type="submit">`'
        details:
          - 'Every form needs a button.'
      - name: '`<label for="…">`'
        details:
          - 'Adds a name to any field.'
          - '**Every field must have a label.**'
      - name: '`<input id="…" type="…">`'
        details:
          - 'Adds an input field of varying [types](#input-types).'
          - '*Must always have an `id` to associate a label.*'
          - 'The `type="…"` attribute defaults to `text`.'
      - name: '`<textarea id="…">`'
        details:
          - 'Adds a large, multi-line text field.'
          - '*Must always have an `id` to associate a label.*'
      - name: '`<select id="…">`'
        details:
          - 'Creates a drop-down choice input.'
          - 'Populate the choices with `<option>` tags.'
          - '*Must always have an `id` to associate a label.*'
      - name: '`<datalist id="…">`'
        details:
          - 'Creates a list of items for autocompletion.'
          - 'Populate the choices with `<option>` tags.'
          - '*Won’t be visible until the associated field is typed into.*'
      - name: '`<option>`'
        details:
          - 'Creates an entry inside `<select>` or `<datalist>`.'
          - 'Use the `selected` attribute to set a default value.'
          - '*For select:* `<option>Triceratops</option>`'
          - '*For datalist:* `<option value="Pteranodon">`'
      - name: '`<optgroup label="…">`'
        details:
          - 'Creates a group of options inside a `<select>`.'
          - '`label="…"` is used as a visible name for the group.'

  - title: 'Input types'
    items:
      - name: '`text` *default*'
        details:
          - 'Single line text field.'
      - name: '`number`'
        details:
          - 'Accepts numbers; has a up/down switch.'
      - name: '`email`'
        details:
          - 'Accepts valid email addresses.'
      - name: '`tel`'
        details:
          - 'For telephone numbers.'
      - name: '`url`'
        details:
          - 'Accepts a valid website URL.'
      - name: '`password`'
        details:
          - 'For passwords; hides typed characters.'
      - name: '`time`'
        details:
          - 'For accepting time: hours, minutes, seconds.'
      - name: '`date`'
        details:
          - 'For accepting dates; shows a calendar picker.'
      - name: '`color`'
        details:
          - 'For picking a specific colour; shows a colour palette.'
      - name: '`range`'
        details:
          - 'For selecting from a range of numbers.'
      - name: '`file`'
        details:
          - 'For choosing a file to upload.'
      - name: '`search`'
        details:
          - 'Specifies the input as a search field.'
          - ''
      - name: '`checkbox`'
        details:
          - 'Turns the input into a check toggle.'
      - name: '`radio`'
        details:
          - 'Turns the input into a radio button.'
          - 'All radio buttons in the group should have the same `name="…"`'
      - name: '`hidden`'
        details:
          - 'Makes the input field invisible.'

  - title: 'Input attributes'
    note: 'Some of these attributes also apply to select and textarea.'
    items:
      - name: '`required`'
        details:
          - 'Define the input as being compulsory.'
          - '`<input id="dino" required>`'
      - name: '`checked`'
        details:
          - 'Whether the `radio` or `checkbox` are selected.'
          - '`<input type="checkbox" id="dino" checked>`'
      - name: '`value="…"`'
        details:
          - 'Puts a default value into the field.'
          - '`<input type="range" value="4" id="dino">`'
      - name: '`placeholder="…"`'
        details:
          - 'Adds a temporary, helpful hint into the field.'
          - '`<input type="email" placeholder="dino@extinct.com" id="email">`'
          - '**Do not use this as a replacement for `<label>`**'
      - name: '`autocomplete="off"`'
        details:
          - 'Disable auto completion in the field.'
      - name: '`autocapitalize="none"`'
        details:
          - 'Disable auto capitalization in the field.'
          - '*Non-standard: only works in iOS.*'
      - name: '`list="…"`'
        details:
          - 'The `id` of an associated a `<datalist>`'
      - name: '`maxlength="…"`'
        details:
          - 'For setting a maximum number of characters.'
          - '`<input type="email" maxlength="256" id="email">`'
      - name: '`minlength="…"`'
        details:
          - 'For setting a minimum number of characters.'
          - '`<input type="text" minlength="6" id="postal-code">`'
      - name: '`min="…"`'
        details:
          - 'Sets a minimum numerical value on `range` & `number`.'
          - '`<input type="number" min="5" id="dino">`'
      - name: '`max="…"`'
        details:
          - 'Sets a maximum numerical value on `range` & `number`.'
          - '`<input type="range" max="100" id="dino">`'
      - name: '`step="…"`'
        details:
          - 'Controls how the number will increment in `range` & `number`.'
          - '`<input type="number" step="0.1" id="dino">`'
      - name: '`pattern="…"`'
        details:
          - 'A Javascript regular expression to control what is valid input.'
          - '`<input type="text" pattern="[A-Za-z][0-9][A-Za-z] ?[0-9][A-Za-z][0-9]" id="postal-code">`'
      - name: '`multiple`'
        details:
          - 'For allowing multiple entries in the field.'
          - '*Works for:* `<select>`, `email`, `file`'
      - name: '`readonly`'
        details:
          - 'Stops the user from modifying the value of the field.'
      - name: '`disabled`'
        details:
          - 'Stops any interaction on the field.'
      - name: '`autofocus`'
        details:
          - 'When the page loads, this field will be focused.'
          - '*Be really careful, only use this when the whole purpose of the page is to fill the form.*'

  - title: 'CSS properties'
    items:
      - name: '`:focus`'
        details:
          - ''
          - ''
      - name: '`:optional`'
        details:
          - ''
          - ''
      - name: '`:required`'
        details:
          - ''
          - ''
      - name: '`:valid`'
        details:
          - ''
          - ''
      - name: '`:invalid`'
        details:
          - ''
          - ''
      - name: '`:checked`'
        details:
          - ''
          - ''
      - name: '`:disabled`'
        details:
          - ''
          - ''
      - name: '`:enabled`'
        details:
          - ''
          - ''
      - name: '`:in-range`'
        details:
          - ''
          - ''

  - title: 'Examples'
    items:
      - name: '*Simple form*'
        details:
          - |
            ```
            <form method="post" action="//formspree.io/dino@extinct.com">
              <label for="email">Email address</label>
              <input type="email" id="email" required>
              <button type="submit">Sign up!</button>
            </form>
            ```
      - name: '*Radio button group*'
        details:
          - |
            ```
            <fieldset>
              <legend>Favourite dinosaur</legend>
              <input type="radio" id="trex" name="dinos">
              <label for="trex">T. rex</label>
              <input type="radio" id="tri" name="dinos">
              <label for="tri">Triceratops</label>
              <input type="radio" id="stego" name="dinos">
              <label for="stego">Stegosaurus</label>
            </fieldset>
            ```
      - name: '*Autocomplete field*'
        details:
          - |
            ```
            <label for="province">Province</label>
            <input id="province" list="province-list" required>
            <datalist id="province-list">
              <option value="Alberta">
              <option value="Ontario">
              <option value="Quebec">
              <option value="Nova Scotia">
            </datalist>
            ```
---
