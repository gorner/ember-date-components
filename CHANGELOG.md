# Changelog

v5.0.0-alpha.0

- [INTERNAL] Update dependencies
- [BREAKING] Require Ember v4.12+ and ember-basic-dropdown v8+; see README for more information.
- [BREAKING] If you used the original ember-date-components, you will need to update any `import` statements to use `from '@gorner/ember-date-components/...';`.

v4.0.1

- [BUGFIX] Ensure date picker can be re-opened after closing it [#199](https://github.com/mydea/ember-date-components/pull/199)

v4.0.0

- Refactor all components to Glimmer components [#189](https://github.com/mydea/ember-date-components/pull/189)
- Allow to yield named blocks for `<DateTimePicker>` [#190](https://github.com/mydea/ember-date-components/pull/190)
- Allow to provide custom component for `<TimePicker>` [#192](https://github.com/mydea/ember-date-components/pull/192)
- Ensure ember-moment is installed when installing this addon [#191](https://github.com/mydea/ember-date-components/pull/191)

BREAKING CHANGES:

- Rename `action` argument to `onChange` (See: [#189](https://github.com/mydea/ember-date-components/pull/189))
- If you used to extend some of the components, you will probably need to adjust that code. Everything that used to be a computed property is now a native getter and needs to be adjusted accordingly - please check the source code directly for these cases.

Not really a breaking change, but v4 really enforces the data down, actions up approach. It will now assert that `@onChange` is set and present and only show the passed in values, never any internal state.


v3.1.0

- Add disabled option for Ember Basic Dropdown to datetime picker
- [INTERNAL] Update dependencies

v3.0.0

- [INTERNAL] Update ember-basic-dropdown to 3.x
- [BREAKING] Require ember-source 3.13+ (due to the ember-basic-dropdown update)

v2.1.2

- [INTERNAL] Fix linting issues & ensure tests run for PRs

v2.1.1

- [BUGFIX] Ensure min & max options work [#138] - thanks @dmaok

v2.1.0

- [BUGFIX] Ensure months are correctly re-rendered in newer Ember versions
- [BUGFIX] Fix button styles to be `min-width` instead of `width` to allow growing
- [INTERNAL] Update all dependencies
- [INTERNAL] Mov to Github Actions for CI

v2.0.6

- Add `selectDateRange()` test helper on date-picker test helper object

v2.0.5

- Stop using `attrs` in component
- Avoid overwriting computed properties

v2.0.4

- [BUGFIX] Do not trigger form submission when selecting time [#31](https://github.com/mydea/ember-date-components/issues/31) - by adding role=button to all buttons

v2.0.3

- Improve focus styling of date-picker
- [BUGFIX IE11] Use `document.body.contains()` instead of `document.contains()` - as IE11 does not support that
- [BUGFIX] Make sure it works without array prototype extensions
- [INTERNAL] Update dependencies

v2.0.2

- Fix `date-picker-inline` navigation

v2.0.1

- Add `time-picker__trigger` class to time picker ember-basic-dropdown trigger for styling

v2.0.0

- Add `selectDate` test helper
- Improve usability of date-picker with keyboard
- Refactor time-picker to be more keyboard friendly
- Introduce new test helpers for date picker: `import { selectDate, getSelectedDate, selectDateTime } from '@gorner/ember-date-components/test-support/helpers/date-picker'`
- Introduce new test helpers for time picker: `import { selectTime, getSelectedTime } from '@gorner/ember-date-components/test-support/helpers/time-picker'`
- Remove old test selectors (e.g. `data-test="day..."`)
- Remove deprecated `interactWithDatePicker` test helper
- Make sure `selectDate` test helper takes year into account

v1.2.3

- Add `amPm` option to `date-time-picker` component

v1.2.2

- Add `buttonDateFormat` option to `date-time-picker` component

v1.2.1

- Ensure the sass partial can be included from your app

v1.2.0

- Fix initialization of selectedDates (Fixes #20)
- Add new test helper: `ember-date-components/test-support/helpers/date-picker`
- Deprecate old test helper at `ember-date-components/helpers/interact-with-date-picker`
- Ensure ember-basic-dropdown setup is correctly invoked (Fixes #17)
- Update ember-cli-htmlbars@3.0.0

v1.1.5

- Add basic assertions in interact-with-date-picker helper
- Add missing test selectors to date-picker-inline
- [INTERNAL] Update dependencies & fix code highlighting in dummy app

v1.1.4

- Update `ember-basic-dropdown` dependency to 1.0.0

v1.1.3

- Add `.selectDate()` method, which will replace the `.select()` method for the `interactWithDatePicker` helper. This is async and will handle dates in different months. `.select()` will continue to work for now, but is deprecated and will be removed in v2.0.0.

v1.1.2

- Fix bug with `interactWithDatePicker` when passing it a jQuery element (fixes #16)

v1.1.1

- Add `disabledDates` attribute to date-picker (via #15 - thanks to @ehubbell)

v1.1.0

- Update all dependencies (incl. update to Ember 3)
- Move to new test syntax
- Drop all usage of jQuery
- [POTENTIALLY BREAKING]: Refactor interactWithDatePicker to use new @ember/test-helpers instead of jQuery

v1.0.6

- Bugfix: Do not parse time when entering a space

v1.0.5

- Allow yielding a custom button for date-picker
- Update dependencies

v1.0.4

- Bugfix: Check for empty value in date-time-picker

v1.0.3

- Add date-time-picker component
- Update dependencies

v1.0.2

- Add renderInPlace option (Thanks @PromoRepublic)
- Add horizontalPosition & verticalPosition options (Thanks to @Nikash)
- Bump ember-basic-dropdown (Thanks to @mixonic)

v1.0.1

- Fix bug where time select would sometimes not fire action

v1.0.0

- Refactor to use ember-basic-dropdown
- Add month & year picker
- Add `startWeekOnSunday` option (PR by rafael-paiva via https://github.com/mydea/ember-date-components/pull/6)

v0.6.1

- Add `interactWithDatePicker` helper at `ember-date-components/helpers/interact-with-date-components` for tests

v0.6.0

- Fix bug that incorrectly checked if parameters where moment instances
- Add `{{date-picker-inline}}` component

v0.5.4

- Minor bugfix release

v0.5.3

- Minor bugfix release

v0.5.2

- Add `disabled` attribute to date-picker & time-picker

v0.5.1

- Use time-picker's ID to build the input's ID (e.g. `my-id` -> `my-id-input`)

v0.5.0

- Add time-picker component

v0.4.0

- Allow selection of to-date without from-date
- to-date should always be `endOf('day')` (e.g. 23:59:59)

v0.3.2

- Move to selected month when switching between from- and to-date
- Fix bug which did not open to-field if no to-field has been selected

v0.3.1

- Fix bug if a null value is given to the date picker
- Set isToStep to false when closing the date picker
- Refactor the Sass partial to be under 'ember-date-components/addon'
- Send closeAction after all data has processed

v0.3.0

- Split date range picker into two separate input fields
- Add closeAction action

v0.2.0

- Complete refactor of date-picker
- Combine date-range-picker into date-picker
- Add custom options

v0.1.0

- Initial Release
