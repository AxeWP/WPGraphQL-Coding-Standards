# Changelog for WPGraphQL Coding Standards

All notable changes to this project will be documented in this file.

This projects adheres to [Semantic Versioning](https://semver.org/) and [Keep a CHANGELOG](https://keepachangelog.com/).

## [ Unreleased ]

## [ 2.1.0 ] - 2026-01-18

This release adds support for the latest alpha versions of PHPCompatibility and PHPCompatibilityWP, and makes a few accompanying changes to the rulesets.

## WPGraphQL-Minimum
- feat: Add additional `@phpstan-*` properties to `SlevomatCodingStandard.Namespaces.FullyQualifiedClassNameInAnnotation.ignoredAnnotationNames`.
- feat: Exclude deprecated `WordPressVIPMinimum.JS` ruleset.

## WPGraphQL-Extra
- feat: Add `Squiz.WhiteSpace.FunctionSpacing` to `WPGraphQL-Extra` ruleset to limit max. consecutive blank lines to 1 instead of 2.

## Misc

- dev: Add support for PHPCompatibility v10-alpha and PHPCompatibilityWP v3-alpha.
- docs: Update example ruleset to default to PHP 8.2 and WP 6.5.
- ci: Update GitHub workflow with latest action versions.
- ci: Add `dependabot.yml` config for GitHub workflows.
- chore: Address misc formatting nits.


## [ 2.0.1 ] - 2025-05-03

This release fixes several bugs where rules were not being disabled correctly.

We've also added CI to the repo to test the rulesets against the latest WPGraphQL codebase, to preemptively catch future issues.

### WPGraphQL-Core

- fix: Fix incorrect excludes XML block in `WPGraphQL-Core` ruleset.

### WPGraphQL-Docs

- fix: Disable `Squiz.Commenting.VariableComment.MissingVar` in favor of `SlevomatCodingStandard.TypeHints.PropertyTypeHint`.

### WPGraphQL-Minimum
- fix: Ignore `SlevomatCodingStandard.Namespaces.FullyQualifiedClassNameInAnnotation` for PHPStan annotations.

### Misc

- ci: Add test workflow.
- docs: cleanup Readme.

## [2.0.0] - 2025-02-15

This release updates the `WPGraphQL-Core` ruleset to match the latest changes included in WPGraphQL [v2.0.0](https://github.com/wp-graphql/wp-graphql/releases/tag/v2.0.0).

It also marks the first v2.0 "stable" release of the WPGraphQL Coding Standards. While it coincides with WPGraphQL v2.0, it's more of a reflection of the stability of the ruleset that these were the only changes needed to WPGraphQL or these rulesets since April 2020.

### WPGraphQL-Core

- Added `WordPress.NamingConventions.ValidFunctionName.MethodNameInvalid`.
- Added `SlevomatCodingStandard.TypeHints.NullableTypeForNullDefaultValue.NullabilityTypeMissing`.

## [2.0.0-beta.3] - 2024-04-05

This release explicitly adds `Squiz.WhiteSpace.SuperfluousWhitespace` to the `WPGraphQL-Extra` ruleset, as it is silenced by VIPCS.

### WPGraphQL-Extra
- Added `Squiz.WhiteSpace.SuperfluousWhitespace` and made explicit.

## [2.0.0-beta.2] - 2023-11-5

This release updates the ruleset based on the latest changes to WPGraphQL core (v1.18.0). Specifically:

### WPGraphQL-Minimum
- Added `PHPCompatibility.Keywords.ForbiddenNamesAsDeclared.objectFound`.
- Moved `SlevomatCodingStandard.Classes.RequireSelfReference` from `WPGraphQL-Strict`.
- Moved `SlevomatCodingStandard.TypeHints.ReturnTypeHint.LessSpecificNativeTypeHint` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.Variables.UselessVariable` from `WPGraphQL-Extra`.

### WPGraphQL-Strict
- Moved `SlevomatCodingStandard.Namespaces.AlphabeticallySortedUses` from `WPGraphQL-Extra`.
- Added `SlevomatCodingStandard.TypeHints.NullableTypeForNullDefaultValue`.
- Added `SlevomatCodingStandard.TypeHints.NullTypeHintOnLastPosition`.
- Moved `SlevomatCodingStandard.TypeHints.ParameterTypeHint.MissingAnyTypeHint` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.PropertyTypeHint.MissingAnyTypeHint` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.ReturnTypeHint.MissingAnyTypeHint` from `WPGraphQL-Extra` and made explicit.

### WPGraphQL-Docs
- Added `Squiz.Commenting` subset of `WordPress-Docs`.
- Added `SlevomatCodingStandard.TypeHints.LongTypeHints`.
- Moved `SlevomatCodingStandard.TypeHints.ParameterTypeHint.MissingTraversableTypeHintSpecification` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.ParameterTypeHint.UselessAnnotation` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.ParameterTypeHint.UselessSuppress` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.ParameterTypeHintSpacing` from `WPGraphQL-Extra`.
- Moved `SlevomatCodingStandard.TypeHints.PropertyTypeHint.MissingTraversableTypeHintSpecification` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.PropertyTypeHint.UselessSuppress` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.ReturnTypeHint.MissingTraversableTypeHintSpecification` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.ReturnTypeHint.UselessAnnotation` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.ReturnTypeHint.UselessSuppress` from `WPGraphQL-Extra` and made explicit.
- Moved `SlevomatCodingStandard.TypeHints.ReturnTypeHintSpacing` from `WPGraphQL-Extra`.

### WPGraphQL-Core
- Added `WPGraphQL-Docs` with some exceptions.

## [2.0.0-beta.1] - 2023-09-17

This release requires WPCS 3.0.0 or higher. Please read the [WordPressCS 3.0 upgrade guide](https://github.com/WordPress/WordPress-Coding-Standards/wiki/Upgrade-Guide-to-WordPressCS-3.0.0-for-ruleset-maintainers) for instructions on how to update your local rulesets and code annotations.

- feat!: Bumped minimum WPCS and VIPCS versions to `3.0.0`.
- fix!: Remove unused `WordPress.CodeAnalysis.AssignmentInCondition.Found` exclusion from `WPGraphQL-Minimum`.
- feat!: Add `Generic.CodeAnalysis.UnusedFunctionParameter` and `WordPress.WP.Capabilities.Undetermined` sniffs to `WPGraphQL-Strict`. These sniffs are excluded from the `WPGraphQL-Core` standard.

## [1.0.0-beta.4] - 2023-08-17
- feat!: Updated `WPGraphQL-Minimum` and `WPGraphQL-Strict` based on the latest changes to WPGraphQL core. (See https://github.com/wp-graphql/wp-graphql/compare/release/v1.14.10...develop#diff-05ae9cddcaec1e845771a7db224961439f83ef5939ec67d3a48744cb34d7e58b)
- feat: Add `WPGraphQL-Core` coding standard, for a snapshot of what's currently being used upstream.

## [1.0.0-beta.3] - 2023-08-04
- feat!: Move `WordPress.WP.I18n.MissingTranslatorsComment` from `WPGraphQL-Strict` to `WPGraphQL-Minimum`. (Added to WPGraphQL in https://github.com/wp-graphql/wp-graphql/pull/2856)
- feat!: Move `SlevomatCodingStandard.Functions.StaticClosure` from `WPGraphQL-Strict` to `WPGraphQL-Minimum`. (Added to WPGraphQL in https://github.com/wp-graphql/wp-graphql/pull/2855)
- chore: Update `slevomat/coding-standard` to `8.13.4`.
- chore: Update Composer dev-deps.

## [1.0.0-beta.2] - 2023-06-17
- dev: Remove `Squiz.Commenting.FunctionComment.ParamCommentFullStop` and `Squiz.Commenting.FunctionComment.EmptyThrows` from `WPGraphQL-Strict`.
- dev: Update minimum PHPUnit version to `8.5.0`.
- chore: Update `phpcs.xml.dist.example` to set the schema location `cache` and `severity` values, and add additional inline-comments.

## [1.0.0-beta.1] - 2023-06-05
- Initial release
