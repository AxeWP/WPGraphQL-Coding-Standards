# Changelog for WPGraphQL Coding Standards

All notable changes to this project will be documented in this file.

This projects adheres to [Semantic Versioning](https://semver.org/) and [Keep a CHANGELOG](https://keepachangelog.com/).

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
- Added`Squiz.Commenting` subset of `WordPress-Docs`.
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
