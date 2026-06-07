# Space Datapad Theme

A custom sci-fi datapad visual theme for Foundry VTT journals, Monk's Enhanced Journal, and chat.

This module packages a standalone CSS stylesheet so it can be enabled directly through Foundry VTT's **Manage Modules** screen. It does **not** require the old Custom CSS module.

## Features

- Sci-fi datapad styling for journal reading views
- Monk's Enhanced Journal support
- Styled read-aloud / show-to-players journal views
- Themed journal window titles
- Sidebar cleanup for Monk's Enhanced Journal
- Chat panel, message, dice roll, and input styling
- Edit-mode safety resets to keep TinyMCE and ProseMirror readable

## Compatibility

Designed for:

- Foundry VTT v11
- Monk's Enhanced Journal

The CSS may also work on later Foundry versions, but selectors can change between Foundry releases. If using Foundry v12 or v13, test journal editing and chat display after enabling the module.

## Installation

Create a folder in your Foundry user data directory:

```text
Data/modules/space-datapad-theme/
```

Your module should use this structure:

```text
space-datapad-theme/
  module.json
  README.md
  styles/
    space-datapad-theme.css
```

Place the stylesheet in:

```text
styles/space-datapad-theme.css
```

Then add a `module.json` file:

```json
{
  "id": "space-datapad-theme",
  "title": "Space Datapad Theme",
  "description": "A custom sci-fi datapad CSS theme for Foundry VTT journals, Monk's Enhanced Journal, and chat.",
  "version": "1.0.0",
  "authors": [
    {
      "name": "Hayden Trask"
    }
  ],
  "compatibility": {
    "minimum": "11",
    "verified": "11"
  },
  "styles": [
    "styles/space-datapad-theme.css"
  ]
}
```

Restart Foundry VTT, open your world, go to **Manage Modules**, and enable **Space Datapad Theme**.

## Updating Compatibility

If you are using a newer Foundry version and have tested that the theme works, you can update the compatibility block in `module.json`.

For example, for Foundry v13:

```json
"compatibility": {
  "minimum": "11",
  "verified": "13"
}
```

## Custom CSS Module Requirement

This module does not require Custom CSS or any other CSS-injection module.

Foundry loads the stylesheet directly from the module manifest using the `styles` array in `module.json`.

## Notes

This theme includes specific safety rules for edit mode. These rules intentionally keep TinyMCE, ProseMirror, form fields, and journal title inputs light and readable while the displayed journal pages use the darker datapad style.

If text becomes unreadable while editing a journal entry, check whether another theme or module is overriding editor styles after this module loads.

## Troubleshooting

### The module does not appear in Manage Modules

Check that:

- The folder name is exactly `space-datapad-theme`
- `module.json` is directly inside that folder
- The `id` in `module.json` is exactly `space-datapad-theme`
- Foundry VTT was restarted after adding the module folder

### The CSS does not apply

Check that:

- The module is enabled for the world
- The stylesheet exists at `styles/space-datapad-theme.css`
- The `styles` path in `module.json` matches the actual file path
- Your browser cache has been refreshed

### Journal edit mode is hard to read

This stylesheet includes edit-mode reset rules, but other modules or themes may override them. Try disabling other visual theme modules temporarily to identify conflicts.

## License

Personal use and table use are permitted. Add a specific open-source license if you plan to publish or distribute the module publicly.
