## sunrise

[![](https://img.shields.io/crates/l/sunrise-next)][license]
[![](https://img.shields.io/crates/v/sunrise-next)][crate]
[![](https://img.shields.io/docsrs/sunrise-next)][docs]

**This is a fork of [nathan-osman][upstream]'s crate to test new features.**

This crate provides a function for calculating sunrise and sunset times using [this method](https://en.wikipedia.org/wiki/Sunrise_equation#Complete_calculation_on_Earth).

### Usage

In order to perform the calculation, you'll need to provide the following:

- the date for which you wish to calculate the times
- the latitude and longitude of the location

Begin by adding this crate to `Cargo.toml`:

```toml
[dependencies]
sunrise = "1.0.0"
```

Next, add a declaration for the crate:

```rust
extern crate sunrise;
```

You can `use` the `sunrise_sunset` function to perform the calculation:

```rust
// Calculate times for January 1, 2016 in Toronto
let (sunrise, sunset) = sunrise::sunrise_sunset(
    43.6532,
    -79.3832,
    2016,
    1,
    1,
);
```

[crate]: https://crates.io/crates/sunrise-next "crates.io"
[docs]: https://docs.rs/sunrise-next "Documentation"
[license]: http://opensource.org/licenses/MIT "MIT License"
[upstream]: https://github.com/nathan-osman/rust-sunrise "Upstream Repository"
