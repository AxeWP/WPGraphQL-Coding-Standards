# WPGraphQL Coding Standards for [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)

This project is a collection of rules and sniffs for PHPCS to validate code developed for the [WPGraphQL](https://github.com/wp-graphql/wp-graphql) ecosystem. It uses rules from:
 - [WordPress Coding Standards](https://github.com/WordPress/WordPress-Coding-Standards)
 - [Automattic VIP Coding Standards](https://github.com/Automattic/VIP-Coding-Standards)
 - [Slevomat Coding Standard](https://https://github.com/slevomat/coding-standard)
 - [PHPCompatibility](https://github.com/PHPCompatibility/PHPCompatibility) & [PHPCompatibilityWP](https://github.com/PHPCompatibility/PHPCompatibilityWP)

## Why use these standards?

Shared coding standards are a great way to ensure consistency in your codebase. They also help to avoid common pitfalls and mistakes, which in turn helps to reduce bugs and technical debt.

These sorts of issues are particularly relevant in the WPGraphQL ecosystem, where we must create robust, performant and type-safe code that often relies on legacy PHP and WordPress code.

Additionally, by ensuring all developers are following the same guidelines and best practices, we can make it easier to collaborate on projects and ensure they stay up-to-date and compatible with WPGraphQL core and other ecosystem plugins.

While currently this ruleset only contains a collection of sniffs from other projects, we hope to add more custom sniffs in the future to help with common issues in the WPGraphQL ecosystem (e.g. ensuring properly named GraphQL types, description formatting, lazy-loaded fields, etc).

## Rulesets

The project provides a superset of sniffs that the WPGraphQL community may need. If you use the `WPGraphQL` standard you will get all the checks.

You can use the following standard names when invoking `phpcs` to select the sniffs you want to use.

* [`WPGraphQL`](./WPGraphQL/ruleset.xml) - complete set with all of the sniffs in the project.
  - [`WPGraphQL-Minimum`](./WPGraphQL-Minimum/ruleset.xml): basic ruleset for WPGraphQL projects.
  - [`WPGraphQL-Strict`](./WPGraphQL-Strict/ruleset.xml): includes all the sniffs in the `WPGraphQL-Minimum` ruleset, plus additional functional sniffs to help you produce enterprise-ready code.
	- [`WPGraphQL-Core`](./WPGraphQL-Core/ruleset.xml): includes all the sniffs currently used by the [WPGraphQL core project](https://github.com/wp-graphql/wp-graphql/blob/develop/phpcs.xml.dist). Currently this is the same as the `WPGraphQL-Strict` ruleset, with a few sniffs disabled.
  - [`WPGraphQL-Extra`](./WPGraphQL-Extra/ruleset.xml): includes all the sniffs in the `WPGraphQL-Strict` ruleset, plus additional formatting sniffs to keep your code looks consistent across your project.
  - [`WPGraphQL-Docs`](./WPGraphQL-Docs/ruleset.xml): includes sniffs for doc-blocks and inline comments.

## Installation

The recommended way to install this project is with [Composer](https://getcomposer.org/). Run the following command to install it into your project:

```bash
composer require --dev axepress/wp-graphql-cs
```

This will install the latest compatible versions of PHPCS and _all the external sniffs and rulesets_, so there is no need to include them in your dependencies list.

We recommend the [PHP_CodeSniffer Standards Composer Installer Plugin](https://github.com/Dealerdirect/phpcodesniffer-composer-installer), which handles the registration of all of the installed standards, so there is no need to set the `installed_paths` config value manually, for single or multiple standards.

For more information about installation and usage, see the [WPCS readme](https://github.com/WordPress/WordPress-Coding-Standards#Installation).

## Configuring your custom ruleset.

> To quick-start your project, you can copy the [example config file](./phpcs.xml.dist.example) to your project root and rename it to `.phpcs.xml.dist`, then update the individual values as explained below.

The best way to use these sniffs in your project is to create a [local configuration file](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Advanced-Usage#using-a-default-configuration-file) that extends the rulesets provided by this project. When you name this file either `.phpcs.xml`, `phpcs.xml`, `.phpcs.xml.dist` or `phpcs.xml.dist`, PHP_CodeSniffer will automatically locate it as long as it is placed in the directory from which you run the CodeSniffer or in a directory above it.

In this file, you will want to configure the following:

- [`testVersion`](./phpcs.xml.dist.example#L33) - The minimum PHP version you want to test against. This should be the lowest version of PHP that you want to support. While WPGraphQL officially supports PHP 7.1+, we recommend testing against PHP 7.3 (the current lowest version actively [tested against](https://github.com/wp-graphql/wp-graphql/blob/develop/.github/workflows/testing-integration.yml)) or higher.
- [`minimum_wp_version`](./phpcs.xml.dist.example#L43) - The minimum WordPress version you want to test against. This should be the lowest version of WordPress that you want to support. While WPGraphQL officially supports WordPress 5.0+, we recommend testing against WordPress 5.6 (the current lowest version actively [tested against](https://github.com/wp-graphql/wp-graphql/blob/develop/.github/workflows/testing-integration.yml)) or higher.
- [`WordPress.WP.I18n.text_domain`](./phpcs.xml.dist.example#L63) - The text domain used in your project. This is used by the `WordPress.WP.I18n` sniff to check that all translatable strings are assigned to a text domain. We recommend using the format `wp-graphql-<project-name>`.
- [`WordPress.NamingConventions.PrefixAllGlobals`](./phpcs.xml.dist.example#L57) - The list of prefixes used in your project. This is used by the `WordPress.NamingConventions.PrefixAllGlobals` sniff to check that all global functions, classes, constants, and variables are prefixed.
