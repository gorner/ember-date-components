# @gorner/ember-date-components

[![Ember Observer Score](https://emberobserver.com/badges/@gorner/ember-date-components.svg)](https://emberobserver.com/addons/@gorner/ember-date-components)

An Ember add-on which provides pure Ember-based date picker components.

This is a fork of the original [ember-date-components](https://github.com/mydea/ember-date-components) which
has been updated to support newer versions of Ember.js and of dependencies like ember-basic-dropdown.
If you cannot use Ember.js v4.12+ and/or ember-basic-dropdown v8+, use the original addon,
which is compatible with ember-basic-dropdown up to v7 if using the `overrides` (npm) or `resolutions` (Yarn)
options in package.json.

## Compatibility

- Ember.js v4.12 or above
- Ember CLI v4.12 or above
- Node.js v18 or above

## Installation

* `ember install ember-moment` - This is a dependency that you will need to install manually. You may also need to manually install `moment` (for `ember-moment` v10+).
* `ember install ember-basic-dropdown` - same; version 8 or above required
* `ember install ember-date-components`
* Additional peer dependencies may be required depending on your setup
* Add `<BasicDropdownWormhole />` to your application.hbs or equivalent, if it isn't there already

## Basic Usage

```hbs
<DatePicker @value={{this.date}} @onChange={{this.updateDate}} />
```

```hbs
<DatePicker @range={{true}} @value={{this.dateRange}} @onChange={{this.updateDateRange}} />
```

```hbs
<TimePicker @value={{this.time}} @onChange={{this.updateTime}} />
```

```hbs
<DateTimePicker @value={{this.date}} @onChange={{this.updateDateTime}} />
```

The date picker can also display custom options, e.g. 'Last 7 days'.

It also provides test helpers to easily interact with the date picker in integration & acceptance tests:

```js
import { selectDate, selectDateRange, getSelectedDate, selectDateTime } from '@gorner/ember-date-components/test-support/helpers/date-picker';
import { selectTime, getSelectedTime } from '@gorner/ember-date-components/test-support/helpers/time-picker';

await selectDate('.my-datepicker', moment());
let momentInstance = await getSelectedDate('.my-datepicker');

await selectTime('.my-timepicker', moment());
let momentInstance = await getSelectedTime('.my-timepicker');

await selectDateTime('.my-date-time-picker', moment());

await selectDateRange('.my-datepicker', dateFrom, dateTo);
```

For more detailed instructions and examples,
please visit the [original repo's documentation](http://mydea.github.io/ember-date-components/).
