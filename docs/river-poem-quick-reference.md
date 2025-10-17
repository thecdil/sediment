# River Poem Quick Reference

## File to Edit
**`_data/river-poem.yml`** - This is your master document for writing the poem

## Basic Structure

```yaml
sections:
  - id: "unique-name"
    scroll_position: 500
    side: "left"
    content: "Your poem text here"
```

## All Properties Cheatsheet

```yaml
- id: "section-name"                    # Required: unique identifier
  scroll_position: 500                  # Required: Y position in pixels
  side: "left"                          # Required: "left" or "right"
  content: "Text here"                  # Required: your poem text
  
  # OPTIONAL - Spacing
  padding_top: 40                       # Default: 20
  padding_bottom: 30                    # Default: 20
  padding_left: 100                     # Default: 20
  padding_right: 80                     # Default: 20
  
  # OPTIONAL - Styling
  max_width: 350                        # Default: 400
  font_size: 16                         # Default: 18
  text_align: "center"                  # Default: "left", options: left/right/center
  animation_delay: 0.5                  # Default: 0 (seconds)
  
  # OPTIONAL - Icon & Link
  icon: "water"                         # Icon filename (without .png)
  link: "/tributaries/water/"           # URL to link to
  link_text: "Explore Water"            # Text next to icon (optional)
```

## Multi-line Text

Use `|` for multi-line poems:

```yaml
content: |
  First line of poem
  Second line continues
  Third line concludes
```

## Available Icons

- water
- land
- atmosphere
- animal
- humans
- infrastructure
- colonization

## CSS Classes Reference

These classes are automatically applied and styled:

- `.poem-section` - Main container
- `.poem-content-box` - Content background box
- `.poem-text` - The poem text itself
- `.poem-branch-left` / `.poem-branch-right` - Connecting lines to river
- `.poem-icon-link` - Icon/link container
- `.is-visible` - Added when section scrolls into view

## Common Patterns

### Simple text only
```yaml
- id: "verse1"
  scroll_position: 300
  side: "left"
  content: "One line of poetry"
```

### Multi-line with link
```yaml
- id: "verse2"
  scroll_position: 700
  side: "right"
  content: |
    Multiple lines
    Of poetic text
  icon: "water"
  link: "/tributaries/water/"
  link_text: "Learn More"
```

### Emphasized section
```yaml
- id: "emphasis"
  scroll_position: 1100
  side: "left"
  content: "Important statement"
  max_width: 400
  font_size: 18
  text_align: "center"
  background_opacity: 1.0
  padding_top: 50
  padding_bottom: 50
```

## Tips

1. **Positioning**: Start sections 300-600px apart
2. **Balance**: Alternate left/right sides
3. **Icons**: Add them near relevant tributary sections
4. **Width**: Wider sections (350-400px) for important verses
5. **Testing**: Save and refresh to see changes immediately

## Workflow

1. Open `_data/river-poem.yml`
2. Add/edit a section
3. Save the file
4. Refresh your browser
5. Adjust `scroll_position` as needed
6. Fine-tune padding and styling
7. Repeat!
