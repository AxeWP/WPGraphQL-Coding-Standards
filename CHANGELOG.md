# Changelog for WPGraphQL Coding Standards

All notable changes to this project will be documented in this file.

This projects adheres to [Semantic Versioning](https://semver.org/) and [Keep a CHANGELOG](https://keepachangelog.com/).

## [Unreleased]

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
