# fink-trial

A slice of Superform's mobile translations, copied verbatim from
`apps/v2-mobile/src/locales`, for trying the [Fink](https://fink.inlang.com) editor.

- Layout: `locales/{locale}/{namespace}.json`, nested keys, ICU MessageFormat inside values
  (i18next + i18next-icu at runtime; Fink reads it via its next-intl plugin).
- Locales: en (base), ru, ro, zh-Hans, pt-BR. Namespaces: onboarding, shared, tx-flow, withdrawal-claim.

## What to check
1. Edit a Russian plural, e.g. `shared` › `timelock.days` (one/few/many/other); the diff should touch one line.
2. Edit a plain string in `ro`; check key order and indentation are untouched.
3. `zh-Hans` / `pt-BR` load under the right tags.
4. `tx-flow` › `chains.payingWithNetworks` (plural inside a sentence) renders and round-trips.
5. Fink flags a translation that drops a `{placeholder}`.
6. Push → branch / PR flow, and what GitHub access Fink's app asks for.
