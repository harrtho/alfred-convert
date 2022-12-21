# Changelog

### [4.0.0][v4.0.0]

Release 2022-12-21

- Update to python 3 and Alfred 4 and 5

### [3.7.0][v3.7.0]

Released 2020-02-20

- Add exchange rates from ExchangeRate-API.com (no API key required)

### [3.6.2][v3.6.2]

Released 2019-09-06

- Include `pkg_resources` (Pint dependency)

### [3.6.1][v3.6.1]

Released 2019-05-30

- Fix argument quoting

### [3.6.0][v3.6.0]

Released 2019-05-06

- Alfred 4 support.

### [3.5.3][v3.5.3]

Released 2019-01-26

- Swap `⌘C` and `↩` to match Alfred's behaviour. `↩` copies result without thousands separator and `⌘C` copies result with separator.

### [3.5.2][v3.5.2]

Released 2019-01-26

- Copy result with or without thousands separator.

### [3.5.1][v3.5.1]

Released 2018-01-13

- Add `CURRENCY_DECIMAL_PLACES` setting to provide alternate number of decimal places for currency conversions.

### [3.5][v3.5]

Released 2018-01-12

- Add `DYNAMIC_DECIMALS` setting to expand the number of decimal places until the displayed result is non-zero.

### [3.4][v3.4]

Released 2017-12-27

- Understand negative numbers in input

### [3.3.1][v3.3.1]

Released 2017-11-21

- Disable currencies with conflicting symbols

### [3.3][v3.3]

Released 2017-11-20

- Parse numbers in accordance with the decimal and thousands separators specified in the workflow configuration

### [3.2.2][v3.2.2]

Released 2017-11-07

- Show warning if user tries to convert fiat currency and `APP_KEY` isn't set
- Ensure cache is cleared after user sets `APP_KEY`

### [3.2.1][v3.2.1]

Released 2017-11-04

- Clear cached data when updated from v<3.1 or when `APP_KEY` is set.

### [3.2][v3.2]

Released 2017-11-02.

- Add support for Pint's contexts #18

### [3.1][v3.1]

Released 2017-11-02.

- Replace Yahoo! Finance with [openexchangerates.org][openx] #27

### [3.0][v3.0]

Released 2017-07-16.

- Option to exclude units when copying #12
- Add per-dimensionality defaults #13
- Option to specify thousands separator #15
- Option to specify custom decimal separator #16
- Add cryptocurrencies #21
- Update Alfred-Workflow
- Update Pint

### [2.6][v2.6]

Released 2017-06-15.

- Fix Sierra forking issue

### [2.5][v2.5]

Released 2015-12-11.

- Fix decoding error

### [2.4][v2.4]

Released 2015-11-28.

- New money icon
- Update pint, docopt and Alfred-Workflow libraries
- Reorganise code and repo

### [2.3][v2.3]

Released 2015-11-26.

- Prevent currencies from clobbering existing units #7
- More precise error messages
- Better query parsing

### [2.2.1][v2.2.1]

Released 2015-07-16.

- Use HTTPS to fetch exchange rates #5
- Improve self-updating
- Use online README instead of bundled file

### [2.2][v2.2]

Released 2015-07-15.

- Add Bitcoin exchange rate #6

### 2.1

Never released.

- Update Alfred-Workflow

### [2.0][v2.0]

Released 2014-12-26.

- Add support for 150+ currencies via Yahoo! Finance #1 #3
- Add support for custom user unit definitions
- Add some additional units to workflow #4
- Configurable number of decimal places in results
- Automatically check for updates (and offer to install them)

### [1.2][v1.2]

Released 2014-08-19.

- Properly handle units containing uppercase letters #2

### [1.1][v1.1]

Released 2014-08-09.

- First release

[v1.1]: https://github.com/deanishe/alfred-convert/releases/tag/v1.1
[v1.2]: https://github.com/deanishe/alfred-convert/releases/tag/v1.2
[v2.0]: https://github.com/deanishe/alfred-convert/releases/tag/v2.0
[v2.2.1]: https://github.com/deanishe/alfred-convert/releases/tag/v2.2.1
[v2.2]: https://github.com/deanishe/alfred-convert/releases/tag/v2.2
[v2.3]: https://github.com/deanishe/alfred-convert/releases/tag/v2.3
[v2.4]: https://github.com/deanishe/alfred-convert/releases/tag/v2.4
[v2.5]: https://github.com/deanishe/alfred-convert/releases/tag/v2.5
[v2.6]: https://github.com/deanishe/alfred-convert/releases/tag/v2.6
[v3.0]: https://github.com/deanishe/alfred-convert/releases/tag/v3.0
[v3.1]: https://github.com/deanishe/alfred-convert/releases/tag/v3.1
[v3.2]: https://github.com/deanishe/alfred-convert/releases/tag/v3.2
[v3.2.1]: https://github.com/deanishe/alfred-convert/releases/tag/v3.2.1
[v3.2.2]: https://github.com/deanishe/alfred-convert/releases/tag/v3.2.2
[v3.3]: https://github.com/deanishe/alfred-convert/releases/tag/v3.3
[v3.3.1]: https://github.com/deanishe/alfred-convert/releases/tag/v3.3.1
[v3.4]: https://github.com/deanishe/alfred-convert/releases/tag/v3.4
[v3.5]: https://github.com/deanishe/alfred-convert/releases/tag/v3.5
[v3.5.1]: https://github.com/deanishe/alfred-convert/releases/tag/v3.5.1
[v3.5.2]: https://github.com/deanishe/alfred-convert/releases/tag/v3.5.2
[v3.5.3]: https://github.com/deanishe/alfred-convert/releases/tag/v3.5.3
[v3.6.0]: https://github.com/deanishe/alfred-convert/releases/tag/v3.6.0
[v3.6.1]: https://github.com/deanishe/alfred-convert/releases/tag/v3.6.1
[v3.6.2]: https://github.com/deanishe/alfred-convert/releases/tag/v3.6.2
[v3.7.0]: https://github.com/deanishe/alfred-convert/releases/tag/v3.7.0
[openx]: https://openexchangerates.org/
