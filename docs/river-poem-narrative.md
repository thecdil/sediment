# River Poem Narrative System - Documentation

This system allows you to add poetic narrative text along your river journey page, with full control over positioning, styling, icons, and links to tributary essays.

## Files Overview

1. **`_data/river-poem.yml`** - Master configuration file where you write and position your poem sections
2. **`_includes/river-poem.html`** - Rendering template (you don't need to edit this)
3. **`main.html`** - Your main river page where you add the include

## Quick Start

### Step 1: Add the include to main.html

In your `main.html` file, add this line where you want the poem sections to appear (after the tributary points, before the closing river-container div):

```html
<!-- Poem Narrative -->
{% include river-poem.html %}
```

### Step 2: Edit the poem configuration

Edit `_data/river-poem.yml` to customize your poem sections.

## Visual Design

The poem sections appear directly on the page without background boxes, allowing the text to sit naturally on your river background. The text features:

- **Larger, readable text** - Default 18px, easily readable as you scroll
- **Subtle text shadow** - Provides contrast against varying backgrounds
- **Italic serif font** - Georgia serif for a literary, poetic feel
- **Bold weight** - Medium-bold (500) for better visibility
- **Enhanced icons** - Larger (50px) with drop shadows for prominence

### Styling Details

The text color is a rich dark brown (`#2C1810`) with a subtle white text shadow that creates a slight glow effect, ensuring readability across your gradient background. Icons are displayed at 50px with enhanced shadows and appear next to optional link text.

## Configuration Options

Each section in `river-poem.yml` supports these properties:

### Required Properties

- **`id`** (string): Unique identifier for the section (e.g., "intro", "verse-1")
- **`scroll_position`** (number): Vertical position in pixels from top of page (e.g., 500)
- **`side`** (string): "left" or "right" - which side of river the section appears
- **`content`** (string): The poem text. Use `|` for multi-line text:
  ```yaml
  content: |
    Line one of the poem
    Line two of the poem
    Line three continues
  ```

### Positioning Properties

- **`padding_top`** (number): Space above content in pixels (default: 20)
- **`padding_bottom`** (number): Space below content in pixels (default: 20)
- **`padding_left`** (number): Space from left edge in pixels (default: 20)
- **`padding_right`** (number): Space from right edge in pixels (default: 20)

### Styling Properties

- **`max_width`** (number): Maximum width of content box in pixels (default: 400)
- **`font_size`** (number): Text size in pixels (default: 18)
- **`text_align`** (string): "left", "right", or "center" (default: "left")
- **`animation_delay`** (number): Delay before appearing in seconds (default: 0)

### Icon and Link Properties

- **`icon`** (string): Filename of icon in `/objects/` folder WITHOUT .png extension
  - Example: `icon: "water"` will use `/objects/water.png`
- **`link`** (string): URL to link to (relative or absolute)
  - Example: `link: "/tributaries/water/"`
- **`link_text`** (string): Text to display next to icon (optional)
  - If not provided, only the icon will show

## Example Configurations

### Basic poem section (text only)

```yaml
- id: "simple-verse"
  scroll_position: 300
  side: "left"
  content: "The river flows through ancient stone"
```

### Multi-line poem with custom styling

```yaml
- id: "styled-verse"
  scroll_position: 600
  side: "right"
  content: |
    From peaks of snow to desert sand
    The waters carve through ancient land
    Carrying stories, grain by grain
  padding_right: 100
  max_width: 400
  font_size: 20
  text_align: "center"
```

### Poem section with icon and link

```yaml
- id: "water-verse"
  scroll_position: 900
  side: "left"
  content: |
    Water shapes the canyon walls
    Polishing stone with patient hands
  padding_left: 120
  icon: "water"
  link: "/tributaries/water/"
  link_text: "Explore Water"
  max_width: 320
```

### Icon link without text label

```yaml
- id: "land-verse"
  scroll_position: 1200
  side: "right"
  content: "Sediment settles in quiet pools"
  icon: "land"
  link: "/tributaries/land/"
```

## Available Icons

Based on your tributary system, these icons should be available in `/objects/`:

- `water`
- `land`
- `atmosphere`
- `animal`
- `humans`
- `infrastructure`
- `colonization`

You can add new icons by placing PNG files in the `/objects/` folder.

## Tips and Best Practices

### Positioning Strategy

1. **Plan your scroll positions** - Space sections 300-600px apart for good rhythm
2. **Alternate sides** - Vary left/right for visual balance
3. **Match river curves** - Position sections near interesting river bends
4. **Test scrolling** - View the page and adjust positions as needed

### Writing Style

1. **Keep it concise** - 1-3 lines per section works best
2. **Use line breaks** - Multi-line format with `|` for poetry
3. **Match tone** - Consider the tributary theme when nearby
4. **Create flow** - Sections should read as a cohesive narrative

### Visual Design

1. **Vary widths** - Use `max_width` to create visual interest
2. **Adjust opacity** - Lower values (0.85-0.90) for subtle backgrounds
3. **Font sizes** - Use larger fonts (16-18px) for emphasis sections
4. **Alignment** - Center-align for standalone verses, left/right for flowing narrative

### Linking Strategy

1. **Strategic placement** - Add links near related tributary sections
2. **Use link text** - Helps users understand what they'll explore
3. **Icon consistency** - Match icon to the linked tributary
4. **Spacing** - Give linked sections more vertical space

## Responsive Behavior

The system automatically adapts for mobile devices:
- Sections center on the page
- Branch lines hide
- Max width reduces to 280px
- Padding adjusts for smaller screens

## Troubleshooting

### Section not appearing
- Check `scroll_position` is within your page height
- Verify `side` is "left" or "right" (lowercase)
- Ensure proper YAML indentation

### Icon not showing
- Confirm PNG file exists in `/objects/` folder
- Check filename matches exactly (case-sensitive)
- Don't include `.png` in the YAML configuration

### Link not working
- Use relative URLs: `/tributaries/water/`
- Or absolute URLs: `https://example.com`
- Test the URL in your browser first

### Styling not applying
- Check for typos in property names
- Ensure numbers don't have quotes
- Verify YAML syntax (no tabs, proper spacing)

## Advanced Customization

### Custom Colors

To change the color scheme, edit the inline styles in `_includes/river-poem.html`:

- Background color: `rgba(245, 222, 179, ...)`
- Text color: `#5D4037`
- Border color: `rgba(210, 105, 30, 0.3)`
- Branch line color: `#D2691E`

### Animation Effects

Modify the animation in the `<style>` section:
- Change transition duration: `transition: all 0.8s ease`
- Adjust entry animation: `transform: translateY(50px)`
- Modify visibility threshold in JavaScript: `threshold: 0.2`

## Example Complete Configuration

Here's a full example showing various configurations:

```yaml
sections:
  - id: "opening"
    scroll_position: 100
    side: "right"
    content: |
      In the beginning, there was water
      Flowing from mountain snow
    padding_right: 80
    max_width: 320
    font_size: 16
    icon: "water"
    link: "/tributaries/water/"
    link_text: "The Source"
    
  - id: "journey"
    scroll_position: 500
    side: "left"
    content: "Through canyon walls it carves its way"
    padding_left: 100
    
  - id: "life"
    scroll_position: 900
    side: "right"
    content: |
      Desert creatures gather here
      Where precious water flows
    icon: "animal"
    link: "/tributaries/animal/"
    text_align: "center"
    font_size: 19
    
  - id: "reflection"
    scroll_position: 1300
    side: "left"
    content: |
      And so the river continues
      Carrying its ancient burden
      Of sediment, memory, and time
    padding_left: 120
    max_width: 420
    font_size: 20
    text_align: "center"
```

## Getting Help

If you encounter issues:
1. Check YAML syntax with an online YAML validator
2. View browser console for JavaScript errors
3. Verify file paths are correct
4. Test one section at a time

---

**Remember**: The beauty of this system is in the iteration. Start with basic sections, view the page, and refine the positioning and styling until it flows perfectly with your river journey!
