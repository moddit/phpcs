# PHP CodeSniffer Project

This project uses PHP_CodeSniffer to ensure that your PHP code adheres to a set of coding standards.

## Requirements

- PHP 8.0 or higher
- Composer

## Installation

1. Install PHP_CodeSniffer via Composer globally:

    ```bash
    composer global require squizlabs/php_codesniffer
    ```

2. Verify the installation:

    ```bash
    phpcs --version
    ```

3. Show the current PHP CodeSniffer ruleset:

    ```bash
    phpcs --config-show
    ```

4. Set the moddit/phpcs as your global PHP CodeSniffer:

    ```bash
    composer global require moddit/phpcs # Installing this package rule set
    phpcs --config-set default_standard ModditPHPCS # Updating default standard ruleset
    ```

## Project ruleset

Your project needs a phpcs.xml file to instantly know which ruleset and folder to lint/format. Create or update the phpcs.xml file in the root of the project as follows. Don't forget to edit the project name and set the files to lint/format:

```xml
<?xml version="1.0"?>
<!-- @see https://pear.php.net/manual/en/package.php.php-codesniffer.annotated-ruleset.php -->
<ruleset name="Project Name"> 
    <file>app</file> <!-- For Laravel -->
    <file>wp/wp-content/themes/blue-headless/includes</file> <!-- For WordPress -->
    <rule ref="ModditPHPCS"></rule> <!-- Our ruleset name -->
</ruleset>
```

## Usage

To check the PHP files in your project, run the following command from your global Composer packages:

```bash
phpcs
```

Or if the project has no phpcs.xml file in the root folder, specify the folder to lint:
```bash
phpcs ./path/to/php
```

## Fixing Code

PHP_CodeSniffer also includes a tool to automatically fix coding standard violations. To use it, run:

```bash
phpcbf ./path/to/your/php/files
```

Or fix all folder files configured in the ruleset of the project's phpcs.xml:

```bash
phpcbf 
```

## IDEA Extensions

### Visual Studio Code

To show `phpcs.xml` lint errors in Visual Studio Code, you can use the following extensions:

- **PHP CodeSniffer**: This extension integrates PHP_CodeSniffer with Visual Studio Code. Including linting and error fixing based on `phpcs.xml`
    ```bash
    ext install shevaua.phpcs
    ```

### PhpStorm

To show `phpcs.xml` lint errors in PhpStorm, you can configure the built-in PHP CodeSniffer integration:

For more detailed instructions, refer to the [PhpStorm documentation](https://www.jetbrains.com/help/phpstorm/using-php-code-sniffer.html#configure-tool-options).


## Contributing

Contributions are welcome! Please submit a pull request or open an issue to discuss any changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.