# Phone

Capture international phone numbers with country selection, local formatting, and E.164 normalization.

```blade
<flux:phone country="US" label="Phone number" />
```

## Basic usage

Use wire:model to bind the phone number to a Livewire property. Flux normalizes possible phone numbers to the international E.164 format, such as +12015550123, while displaying a familiar local format to the user. Set country when you know the user's starting country.

Incomplete or unparseable entries are preserved as typed, so the bound value is not always E.164. Without a selected country, users need to include an international calling code for normalization. Formatting does not validate a phone number or confirm that it can receive calls; validate submitted values on your server.

```blade
<flux:phone wire:model="phone" country="US" />
```

## Default country
Set the country used for an empty number. The selected country updates automatically when a user enters an international number.

```blade
<flux:phone country="GB" />
```

## Country list
Use countries to limit the picker to countries your product supports.

This only controls the picker, not the numbers users can enter. Validate country restrictions on your server.

```blade
<flux:phone :countries="['US', 'CA', 'GB', 'AU']" />
```

## Country order
Use country-order to put common choices first. The remaining countries in the picker follow alphabetically in the app's locale.

```blade
<flux:phone :country-order="['US', 'CA', 'GB', 'AU']" />
```

## Filled
Use the filled variant where other form controls use it.

```blade
<flux:phone variant="filled" />
```

## Sizes
Use the same compact sizes as other Flux inputs.

```blade
<flux:phone size="sm" />
<flux:phone size="xs" />
```

## Disabled and readonly
Use disabled to prevent interaction, or readonly to preserve the value without allowing edits.

```blade
<flux:phone disabled />
<flux:phone readonly />
```

## Invalid
Use invalid to show the same error treatment as Flux inputs.

```blade
<flux:phone invalid />
```

## Reference

### flux:phone
| Prop | Description |
| --- | --- |
| wire:model | Binds the phone number to a Livewire property. Possible numbers are normalized to E.164; incomplete or unparseable entries are preserved as typed. |
| value | Initial phone number as an E.164 string. |
| name | Name submitted with a plain HTML form. |
| country | Initial ISO 3166-1 alpha-2 country code. Omit it when there is no useful default. |
| countries | Array of ISO 3166-1 alpha-2 country codes available in the picker. Does not restrict entered numbers. |
| country-order | Array of country codes shown first in the picker. |
| placeholder | Hint displayed when the phone number is empty. |
| size | Size of the control. Options: sm, xs. |
| variant | Visual style. Options: filled. Default: outline. |
| label | Label text displayed above the control. |
| description | Help text displayed above the control. |
| disabled | Prevents interaction with the country picker and phone number. |
| readonly | Preserves the value while preventing edits. |
| invalid | Applies error styling to the control. |

| Attribute | Description |
| --- | --- |
| data-flux-phone | Applied to the root element for styling and identification. |