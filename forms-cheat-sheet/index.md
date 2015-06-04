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
          - 'Used to group elements together, like radio button groups.'
          - 'Must always have a legend.'
      - name: '`<legend>`'
        details:
          - 'Adds a title to the fieldset.'
          - 'Must be inside a fieldset.'
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
          - 'Must always have an `id` to associate a label.'
          - 'The `type=""` attribute defaults to `text`.'
      - name: '`<textarea id="…">`'
        details:
          - 'Adds a large, multi-line text field.'
          - 'Must always have an `id` to associate a label.'
      - name: '`<select id="…">`'
        details:
          - 'Creates a drop-down choice input.'
          - 'Populate the choices with `<option>` tags.'
          - 'Must always have an `id` to associate a label.'
      - name: '`<option>`'
        details:
          - 'Creates an entry inside a select box.'
          - 'Cannot be outside the `<select>` tag.'
          - '*Attributes:* `checked`, ``'

  - title: 'Input types'
    items:
      - name: '`text` *default*'
        details:
          - ''
          - ''
      - name: '`number`'
        details:
          - ''
          - ''
      - name: '`email`'
        details:
          - ''
          - ''
      - name: '`tel`'
        details:
          - ''
          - ''
      - name: '`url`'
        details:
          - ''
          - ''
      - name: '`password`'
        details:
          - ''
          - ''
      - name: '`time`'
        details:
          - ''
          - ''
      - name: '`date`'
        details:
          - ''
          - ''
      - name: '`color`'
        details:
          - ''
          - ''
      - name: '`file`'
        details:
          - ''
          - ''
      - name: '`search`'
        details:
          - ''
          - ''
      - name: '`checkbox`'
        details:
          - ''
          - ''
      - name: '`radio`'
        details:
          - ''
          - ''
      - name: '`hidden`'
        details:
          - ''
          - ''

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

---
