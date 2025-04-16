# setup-xk6

GitHub action to install the [xk6](https://github.com/grafana/xk6) CLI tool and add it to the `PATH`.

## Usage

```yaml
      - name: Setup go
        uses: actions/setup-go@v5

      - name: Setup xk6
        uses: grafana/setup-xk6@v0.1.0

      - name: Build
        shell: bash
        run: xk6 build --with github.com/grafana/xk6-example

      - name: Version
        shell: bash
        run: ./k6 version
```

## Inputs

name          | default        | description
--------------|----------------|-------------
`dir`         | `~/.local/bin` | The target directory for the installation.
`xk6-version` | `latest`       | The semantic version of xk6 to install, or `latest`.
`cache`       | `true`         | A value of `true` enables caching of the xk6 binary.

## Outputs

name          | description
--------------|-------------
`xk6-version` | The version installed. Useful if `latest` is the input version.
