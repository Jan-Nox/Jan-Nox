---
title: "Projects"
type: page
---

## Validator 💘 Value

### It Began With a Mistake

In 2016, during the hectic initial phase of our startup, we made a critical mistake that impacted several months of invoice provisions for our sales managers. We mistakenly applied the netToGross tax calculation for sales tax multiple times, even on already gross values, leading to significant errors.
This issue went unnoticed for several months, causing considerable trouble. As a result, we developed two separate libraries to ensure valid values across all our platforms.

The first commitment was to ensure valid parameters across the entire projects by creating the Value library. Then, as a logical conclusion, the next step was to implement a standard on how data has to be validated.

```php
class Taxes {
    private const SALES_TAX = 0.15; // Correcting to decimal representation for percentage

    /**
     * Converts a NetValue to a GrossValue by applying the sales tax.
     *
     * @param NetValue $netValue The net value object.
     * @return GrossValue The gross value object.
     */
    public static function getGrossFromNet(NetValue $netValue): GrossValue {
        return new GrossValue($netValue->get() * (1 + self::SALES_TAX));
    }
}
```


#### noxkiwi [Validator](https://validator.nox.kiwi)
- Checks input for integrity.
- Returns one or more detailed pieces of information on why an input is problematic.

#### noxkiwi [Value](https://value.nox.kiwi)
- Can only be constructed with valid input.
- Once constructed, the input is immutable, ensuring integrity during runtime.

# Ensuring Valid Data Across Your Project
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=noxkiwi_value&metric=security_rating)](https://sonarcloud.io/summary/new_code?id=noxkiwi_value)
[![Code Smells](https://sonarcloud.io/api/project_badges/measure?project=noxkiwi_value&metric=code_smells)](https://sonarcloud.io/summary/new_code?id=noxkiwi_value)
[![Lines of Code](https://sonarcloud.io/api/project_badges/measure?project=noxkiwi_value&metric=ncloc)](https://sonarcloud.io/summary/new_code?id=noxkiwi_value)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=noxkiwi_value&metric=alert_status)](https://sonarcloud.io/summary/new_code?id=noxkiwi_value)
