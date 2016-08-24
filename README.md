amazon-orders
=============
Export your orders from amazon.de

Based on the idea of [CyberLine/amazon-parser](https://github.com/CyberLine/amazon-parser),
this allows you to export your orders from amazon.de - without needing or opening a browser window.

This is only tested on amazon.de, since amazon.com offers an [integrated CSV export](https://www.amazon.com/gp/b2b/reports) of your orders, amazon.de does not.

By default this script ignores free orders and orders that were returned and refunded.
Free orders may be included by calling the script with the `--include_free` option,
or passing `include_free=True` to `download_orders`.


## Install
1. `git clone git@github.com:albalitz/amazon-orders.git`
1. `cd amazon-orders`
1. Create a pyvenv: `pyvenv venv`
1. Install the requirements: `venv/bin/pip install -r requirements.txt`


## Use
### Terminal
```shell
usage: amazon_orders.py [-h] [-v] [-j FILE] [-c FILE] [--include_free]

Export your orders from amazon.de.

optional arguments:
  -h, --help            show this help message and exit
  -v, --verbose         Increase the loglevel. More vs = more output.
  -j FILE, --json FILE  Save the orders as json to the specified file.
  -c FILE, --csv FILE   Save the orders as csv to the specified file.
  --include_free        Include free orders.
```

### In another project
Download `amazon_orders.py` to your project and use it like this:

```python
import amazon_orders

orders = amazon_orders.download_orders("asd@example.com", "supersecurepassword1")
```
