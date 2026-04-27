---
components_used: [separator]
---

# Color picker

Let users pick a color from a swatch palette, drag a saturation/value canvas, or paste a hex value. Perfect for theme settings, brand-color pickers, and any place users need to choose a color.

```blade
<flux:color-picker wire:model="theme" />
```

## Format
Pick the output format using the format prop. Supported values: hex (default), hexa (hex with alpha), rgb, rgba (RGB with alpha), hsl, hsla (HSL with alpha). Alpha-aware formats automatically render an alpha slider in the popover.

```blade
<flux:color-picker format="hex" />
<flux:color-picker format="hexa" />
<flux:color-picker format="rgb" />
<flux:color-picker format="rgba" />
<flux:color-picker format="hsl" />
<flux:color-picker format="hsla" />
```

## Sizes
The color picker supports three sizes that match other form components.

```blade
<flux:color-picker />
<flux:color-picker size="sm" />
<flux:color-picker size="xs" />
```

## Button trigger
Use type="button" for a simpler trigger that displays the selected color and opens the popover on click. Useful for compact toolbars or swatches-only pickers where typing isn't needed.

```blade
<flux:color-picker type="button" />
```

## Custom swatches
Replace the default 24-color Tailwind palette with your own brand colors. Pass an array of hex strings to the :swatches prop. You can also pass \[value, label\] pairs for accessible swatch labels.

```blade
<flux:color-picker :swatches="['#ef4444', '#22c55e', '#3b82f6', '#f59e0b', '#a855f7']" />

<!-- With [value, label] pairs for accessible swatch labels -->
<flux:color-picker :swatches="[['#ef4444', 'Red'], ['#22c55e', 'Green'], ['#3b82f6', 'Blue']]" />
```

## No swatches
Pass :swatches="false" to hide the default swatch grid entirely. The popover will only show the SV area, hue slider, and hex input.

```blade
<flux:color-picker :swatches="false" />
```

## Custom layout
Compose flux:color-picker.area, flux:color-picker.slider, flux:color-picker.input, and flux:color-picker.swatches in any order to build a fully custom popover layout.

```blade
<flux:color-picker>
    <div class="flex flex-col gap-3">
        <flux:color-picker.input placeholder="#000000" />
        <flux:separator />
        <flux:color-picker.area />
        <flux:color-picker.slider channel="hue" />
    </div>
</flux:color-picker>
```

## Dropper
Add the dropper prop to render a button that lets users pick a color from anywhere on the screen. Uses the browser's EyeDropper API — automatically disabled in unsupported browsers.

```blade
<flux:color-picker dropper />
```

## Clearable
Add the clearable prop to render a clear (X) button on the trigger when a value is set.

```blade
<flux:color-picker clearable />
```

## Copyable
Add the copyable prop to render a clipboard-copy button on the trigger. One click copies the color value in the configured format. Only available with the default input trigger.

```blade
<flux:color-picker copyable />
```

## Disabled
Prevent interaction and visually dim the trigger.

```blade
<flux:color-picker disabled />
```

## Reference

### flux:color-picker
| Prop | Description |
| --- | --- |
| wire:model | Binds the color picker to a Livewire property. The value is a CSS color string in the configured format. See the wire:model documentation for more information. |
| value | Initial value as any CSS color string. Auto-normalized to the configured format on display. |
| name | Generates a hidden form input with this name for native form submission (no wire:model required). |
| format | Output format. Options: hex (default), hexa, rgb, rgba, hsl, hsla. Alpha-aware formats automatically render an alpha slider in the popover. |
| type | Trigger type. Options: input (default), button. The default input trigger lets users type or paste a color directly. The button trigger shows the value and opens the popover on click. |
| placeholder | Placeholder text for the input trigger. Default: format-specific (e.g. #000000 for hex). |
| size | Trigger size. Options: sm, xs. Default: base. |
| :swatches | Custom swatch palette as an array of hex strings or [value, label] pairs, or false to hide the default swatch grid entirely. |
| dropper | Render a dropper button in the popover that lets users pick a color from the screen. Uses the EyeDropper API — automatically disabled in unsupported browsers. Default: false. |
| clearable | Render a clear (X) button on the trigger when a value is set. Default: false. |
| copyable | Render a clipboard-copy button on the trigger. Only available with the default input trigger. Default: false. |
| label | Field label. Forwarded to flux:with-field. |
| description | Field description. Forwarded to flux:with-field. |
| disabled | Disable the picker. Default: false. |
| invalid | Mark the trigger as invalid. Auto-detected from the field's error bag when bound via wire:model. |

### flux:color-picker.area
| Prop | Description |
| --- | --- |
| class | Additional CSS classes applied to the area element. |

### flux:color-picker.slider
| Prop | Description |
| --- | --- |
| channel | The color channel this slider controls. Options: hue (default), alpha. |

### flux:color-picker.input
| Prop | Description |
| --- | --- |
| placeholder | Placeholder text for the text input. Default: format-specific (e.g. #000000). |

### flux:color-picker.swatches
| Prop | Description |
| --- | --- |
| class | Additional CSS classes applied to the swatches container. |

### flux:color-picker.swatch
| Prop | Description |
| --- | --- |
| value | The color value as a CSS color string (e.g. #ef4444). |
| label | Human-readable label for the swatch. Used as the aria-label and hover tooltip. Defaults to the value. |

### flux:color-picker.dropper
| Prop | Description |
| --- | --- |
| class | Additional CSS classes applied to the dropper element. Automatically disabled in browsers that don't support the EyeDropper API. |