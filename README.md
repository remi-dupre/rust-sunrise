## sunrise

[![](https://img.shields.io/crates/l/sunrise-next)][license]
[![](https://img.shields.io/crates/v/sunrise-next)][crate]
[![](https://img.shields.io/docsrs/sunrise-next)][docs]

**This is a fork of [nathan-osman][upstream]'s crate to test new features.**
[![](https://img.shields.io/crates/l/sunrise)][license]
[![](https://img.shields.io/crates/v/sunrise)][crate]
[![](https://img.shields.io/docsrs/sunrise)][docs]

This crate provides a function for calculating sunrise and sunset times using [this method](https://en.wikipedia.org/wiki/Sunrise_equation#Complete_calculation_on_Earth).

You can enable the **no-std feature** if you need it to work in such a context, it will rely on `libm` instead.

### Usage

In order to perform the calculation, you'll need to provide the following:

- the date for which you wish to calculate the times
- the latitude and longitude of the location

Begin by adding this crate to `Cargo.toml`:

```toml
[dependencies]
sunrise-next = "1.3"
```

You can `use` the `sunrise_sunset` function to perform the calculation:

```rust
// Calculate times for January 1, 2016 in Toronto
let (sunrise, sunset) = sunrise_next::sunrise_sunset(43.6532, -79.3832, 2016, 1, 1);
```

If you need more refined control, you can use the `SolarDay` struct:

```rust
use sunrise_next::{sunrise_sunset, SolarDay, SolarEvent, DawnType};

let dawn = SolarDay::new(43.6532, -79.3832, 2016, 1, 1)
    .with_altitude(54.)
    .event_time(SolarEvent::Dawn(DawnType::Civil));
```

[crate]: https://crates.io/crates/sunrise-next "crates.io"
[docs]: https://docs.rs/sunrise-next "Documentation"
[license]: http://opensource.org/licenses/MIT "MIT License"
[upstream]: https://github.com/nathan-osman/rust-sunrise "Upstream Repository"
