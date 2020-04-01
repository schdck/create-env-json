# create-env-json

This action writes environment variables to a JSON file.

## Inputs

### `fileName`

**Required** The file name.

### `Other variables`

Any other variables you want written.

## Outputs

### `full-path`

The full path to the written file.

## Exemplo de uso

```
uses: schdck/create-env-json@v1
with:
  file-name: 'env.json'
  super-secret: ${{ secrets.SuperSecret }}
  CONNECTION_STRING: ${{ secrets.connection_string }}
  [...]
```