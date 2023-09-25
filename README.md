# Convert Alfred Workflow

[![GitHub Version][shield-version]][gh-releases]
[![GitHub All Releases][shield-downloads]][gh-releases]
[![GitHub][shield-license]][license-mit]

Convert between different units offline in [Alfred][alfred].

**Note:** Currency conversions do require occasional Internet connectivity to update exchange rates. Alfred-Convert will otherwise work just fine without an Internet connection.

![][preview]

## Download & Installation

Download the [latest workflow release][gh-latest-release] from GitHub. Open the workflow file to
install in Alfred.

## Usage

- `conv <quantity> <from unit> [<to unit>]` — Perform a conversion
  - `↩` — Copy result without thousands separator to pasteboard
  - `⌘ + C` — Copy result with thousands separator to pasteboard
  - `⌘ + ↩` — Add/remove destination unit as default for this dimensionality
  - `⌘ + L` — Show result in Alfred's Large Type window
- `convinfo` — View help file and information about the workflow, or edit custom units and active 
    currencies
  - `View Help File` — Open this page in your browser
  - `View All Supported Currencies` — View/filter the list of all supported currencies in Alfred
  - `Edit Active Currencies` — Edit the list of active currencies in your default text editor
  - `Edit Custom Units` — Edit the list of custom currencies in your default text editor

### Conversions

**NOTE**: Only a limited number of fiat currencies are supported by default. Additional rates are
only supported if you set a key for the [openexchangerates.org][openx] API in the workflow's
[configuration sheet](#configuration). You can sign up for a free account [here][openx-free].
When you're signed up, copy the **App ID** from the email you receive or [this page][openx-appid]
into the `APP_KEY` field in the [configuration sheet](#configuration).

- `conv [<context>] <quantity> <from unit> [<to unit>]` — Perform a conversion
  - `↩` or `⌘ + C` — Copy the result to the pasteboard
  - `⌘ + ↩` — Add/remove destination unit as default for this dimensionality
  - `⌘ + L` — Show result in Alfred's Large Type window

If no destination unit is specified, any defaults you've saved will be used (that aren't the same as
the source unit).

The syntax is simple: an optional context, the quantity, the unit you want to convert from then
(optionally) the unit you want to convert to. For example:

- `conv 128 mph kph`
- `conv 72in cm`
- `conv 100psi bar`
- `conv 20.5 m/s mph`
- `conv 100 eur gbp`

Or with a [Context][pintcontext]:

- `conv spectroscopy 1Å eV` (or `conv sp 1Å eV`)

It doesn't matter if there is a space between the quantity and the units or not. Alfred-Convert will
tell you if it doesn't understand your query or know the units.

Actioning an item (selecting it and hitting `↩`) will copy it to the clipboard. Using `⌘ + L` will
display the result in Alfred's large text window, `⌘ + C` will copy the selected result to the
clipboard.

## Configuration

The workflow is configured via the [Workflow Environment Variables][alfred-config-sheet]
(the `[𝒙]` icon) in Alfred Preferences and via a couple of text files in its data directory.

### Configuration Sheet

Basic configuration is performed in the [Workflow Environment Variables][alfred-config-sheet]:

| Option                    | Meaning                                                                                                                                       |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `APP_KEY`                 | API key for [openexchangerates.org][openx].                                                                                                   |
| `COPY_UNIT`               | Include unit when copying conversion result. Any value but `0` or empty turns this option on.                                                 |
| `CURRENCY_DECIMAL_PLACES` | Overrides the default `DECIMAL_PLACES` setting for currency conversions.                                                                      |
| `DECIMAL_PLACES`          | Number of decimal places to show in results.                                                                                                  |
| `DECIMAL_SEPARATOR`       | Character to separate whole numbers and decimal fractions. Used for parsing input and generating output.                                      |
| `DYNAMIC_DECIMALS`        | Dynamically increase the number of decimal places (up to 10) so that the result is non-zero. Any value but `0` or empty turns this option on. |
| `THOUSANDS_SEPARATOR`     | Character to delimit thousands Used for parsing input and generating output.                                                                  |
| `UPDATE_INTERVAL`         | How often (in minutes) to update currency exchange rates.                                                                                     |

### Active Currencies

By default, all supported fiat currencies (provided you've set `APP_KEY` in the
[configuration sheet](#configuration)) and a handful of the most popular cryptocurrencies are
active.

- `convinfo`
  - `View All Supported Currencies`
  - `Edit Active Currencies`

Use `Edit Active Currencies` to open the list of active currencies in your default editor. Add the
symbol for the currency you'd like to activate on a new line in this file.

You can use `View All Supported Currencies` to search for the currency you'd like to activate, then
use `⌘ + C` on the result to copy the symbol to the pasteboard.

### Custom Units

See [Adding Custom Units](#adding-custom-units).

### Supported Units

Currently, Alfred-Convert only supports [the units][pintunits] understood by the underlying
[Pint][pintdocs] library plus [currencies](#supported-currencies) and a handful of additional units.

You can [add your own custom units](#adding-custom-units) to the workflow. If you think they'd be
useful to everyone, please create a corresponding [GitHub issue][gh-issues] to request addition as a
default unit or submit a [pull request][gh-pulls].

### Supported Currencies

To convert, use the appropriate **abbreviation** for the relevant currencies, e.g.
`conv 100 eur gbp`.

You can also view (and search) the list from within Alfred by using the keyword `convinfo` and
choosing `View All Supported Currencies`.

See [All supported currencies](./docs/currencies.md).

### Adding Custom Units

You can add your own custom units using the [format defined by Pint][pinthowto]. Add your
definitions to the `unit_definitions.txt` file in the workflow's data directory.

To edit this file, enter `convinfo` in Alfred and select `Edit Custom Units`. The
`unit_definitions.txt` file will open in your default text editor.

Please see the [Pint documentation][pinthowto] for the required format. See Pint's
[default unit definitions][pintunits] for examples.

## Bug Reports and Feature Requests

Please use [GitHub issues][gh-issues] to report bugs or request features.

## Contributors

This Alfred Workflow comes from the [abandoned Workflow][abandoned-workflow] of
[Dean Jackson][deanishe]

## License

Convert Alfred Workflow is licensed under the [MIT License][license-mit]

The workflow uses the following libraries:

- [Pint][pintrepo] ([BSD License][license-bsd])
- [Alfred-PyWorkflow][alfred-pyworkflow] ([MIT License][license-mit])
- [docopt][docopt] ([MIT License][license-mit])

The workflow uses following icons:

- The workflow icons are from [Font Awesome][fontawesome]


Exchange rates are downloaded from [openexchangerates.org][openx] and [CryptoCompare][cryptocompare]
(for cryptocurrencies).

[abandoned-workflow]: https://github.com/deanishe/alfred-convert
[alfred-pyworkflow]: https://xdevcloud.de/alfred-pyworkflow/
[alfred]: https://www.alfredapp.com/
[alfred-config-sheet]: https://www.alfredapp.com/help/workflows/advanced/variables/#environment
[cryptocompare]: https://www.cryptocompare.com/
[deanishe]: https://github.com/deanishe
[docopt]: https://github.com/docopt/docopt
[fontawesome]: https://fortawesome.github.io/Font-Awesome/
[gh-issues]: https://github.com/harrtho/alfred-convert/issues
[gh-latest-release]: https://github.com/harrtho/alfred-convert/releases/latest
[gh-pulls]: https://github.com/harrtho/alfred-convert/pulls
[gh-releases]: https://github.com/harrtho/alfred-convert/releases
[license-bsd]: https://github.com/hgrecco/pint/blob/master/LICENSE
[license-mit]: https://opensource.org/licenses/MIT
[openx-appid]: https://openexchangerates.org/account/app-ids
[openx-free]: https://openexchangerates.org/signup/free
[openx]: https://openexchangerates.org/
[pintdocs]: https://pint.readthedocs.io/en/latest/index.html
[pinthowto]: https://pint.readthedocs.io/en/latest/user/formatting.html
[pintrepo]: https://github.com/hgrecco/pint
[pintunits]: https://github.com/hgrecco/pint/blob/master/pint/default_en.txt
[pintcontext]: https://pint.readthedocs.io/en/latest/user/contexts.html
[preview]: img/preview.png
[shield-downloads]: https://img.shields.io/github/downloads/harrtho/alfred-convert/total.svg
[shield-license]: https://img.shields.io/github/license/harrtho/alfred-convert.svg
[shield-version]: https://img.shields.io/github/release/harrtho/alfred-convert.svg
