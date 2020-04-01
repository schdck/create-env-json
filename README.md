# create-env-json

This action writes environment variables (or anything you want) to a JSON file that can be accessed by future steps.

## Inputs

* **[required] `file-name`**: The name of the file to be written.
* **Other variables**: you must specify any other variable you want written to the JSON as input variables. Pass the variable with the name you want to appear in the JSON.

## Output

* **`full-path`**: The full path to the written file

## Usage

```
uses: schdck/create-env-json@v1
id: create-env
with:
  file-name: 'env.json'
  super-secret: ${{ secrets.SuperSecret }}
  CONNECTION_STRING: ${{ secrets.connection_string }}
```

#### This will generate the following JSON:

``` json
{"super-secret":"[your-super-secret]","CONNECTION_STRING":"[your-connection-string]"}
```

You can later pass it's path as an input for another program (e.g. [`claudia.js`](https://claudiajs.com/), which receives a JSON in `--set-env-from-json`)

#### Acessing the full-path

You can later access the full path of the file using `${{ steps.create-env.outputs.full-path }}`