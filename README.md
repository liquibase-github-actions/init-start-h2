# Liquibase Init Start H2 Action
Official GitHub Action to run Liquibase Init Start H2 in your GitHub Action Workflow. For more information on how init start h2 works visit the [Official Liquibase Documentation](https://docs.liquibase.com/commands/home.html).
## Init Start H2
Launches H2, an included open source in-memory database. This Java application is shipped with Liquibase, and is useful in the Getting Started experience and for testing out Liquibase commands.
## Usage
```yaml
steps:
- uses: actions/checkout@v3
- uses: liquibase-github-actions/init-start-h2@v4.29.2
  with:
    # Network address to bind to
    # string
    # Optional
    bindAddress: ""

    # Port to run h2 database on
    # int32
    # Optional
    dbPort: ""

    # When set to true, Liquibase initiates the H2 database in a new thread without blocking, allowing use within the flow command. Regardless of the parameter setting, data stored in the H2 database is cleared when the JVM exits, such as at the end of the flow command.
    # bool
    # Optional
    detached: ""

    # Whether to open a browser to the database"s web interface
    # bool
    # Optional
    launchBrowser: ""

    # Password to use for created h2 user
    # string
    # Optional
    password: ""

    # Username to create in h2
    # string
    # Optional
    username: ""

    # Port to run h2"s web interface on
    # int32
    # Optional
    webPort: ""

```

### Secrets
It is a good practice to protect your database credentials with [GitHub Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## Optional Liquibase Global Inputs
The liquibase init start h2 action accepts all valid liquibase global options as optional parameters. A full list is available in the official [Liquibase Documentation](https://docs.liquibase.com/parameters/command-parameters.html).

### Example
```yaml
steps:
  - uses: actions/checkout@v3
  - uses: liquibase-github-actions/init-start-h2@v4.29.2
    with:
      headless: true
      licenseKey: ${{ secrets.LIQUIBASE_LICENSE_KEY }}
      logLevel: INFO
```

## Feedback and Issues
This action is automatically generated. Please submit all feedback and issues with the [generator repository](https://github.com/liquibase/github-action-generator/issues).
