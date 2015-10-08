# jwt-bulk-generator

This is a script to generate [JWTs](http://jwt.io/) and store them in a file.

## Installation

Prerequisites:

* Node JS 0.10.26 or higher (see NodeJS).
* Tools: git and npm.

```sh
git clone https://github.com/TDAF/jwt-bulk-generator.git
cd jwt-bulk-generator
npm install
```

## Running

```sh
node lib/jwt-bulk-generator.js -n 1000 -p examples/payload.json -k examples/key.json -o jwts.csv -e 250000 --prefix "tel:+34"
```

Script options are the following:

```sh
Options:
  -n, --number       Number of JWTs to generate
  -p, --payloadFile  File where the input token payload is stored
  -k, --keyFile      File where the key is stored
  -o, --outputFile   File where the generated tokens will be stored
  -e, --expiration   Expiration for the JWTs, in seconds from now
  --prefix           Prefix for phone numbers in jwt (e.g. tel:+34)
                                                            [defecto: "tel:+34"]
```


## Using templates

See working examples at the examples directory. Note that the script will substitute, for each token, the appearance of ```{{{uuid}}}``` with a freshly generated uuid.v4() and ```{{{phone}}}``` with a freshly generated 9 digits-long phone number.
