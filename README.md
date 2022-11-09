# Run `permifrost`: Github Action

## Usage example

```yaml
name: Run permifrost

on:
  push:
    tags:
      - "*"

jobs:
  run-permifrost:
    runs-on: ubuntu-latest
    name: Run permifrost
    steps:
      - name: Checkout code
        uses: actions/checkout@v3
      - name: Run permifrost
        uses: ariangilesgarcia/run-permifrost@1.0.0-dev.2
        env:
          PERMISSION_BOT_USER: ${{ secrets.PERMISSION_BOT_USER }}
          PERMISSION_BOT_ACCOUNT: ${{ secrets.PERMISSION_BOT_ACCOUNT }}
          PERMISSION_BOT_WAREHOUSE: ${{ secrets.PERMISSION_BOT_WAREHOUSE }}
          PERMISSION_BOT_PASSWORD: ${{ secrets.PERMISSION_BOT_PASSWORD }}
          PERMISSION_BOT_DATABASE: ${{ secrets.PERMISSION_BOT_DATABASE }}
          PERMISSION_BOT_ROLE: ${{ secrets.PERMISSION_BOT_ROLE }}
        with:
          spec: ./permifrost/spec.yaml
```
