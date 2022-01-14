# Breaking up Long Function Calls in Python with Perens

Parenthesis **without a trailing comma** can be used to break up long
function calls into several lines for readability.

Long Single-lined version:

```python
product_sellrates = shop_prod_compatibility.melt(["shop_id", "item_id", "customer_id", "Shop Name"]).dropna().reset_index(drop=True)
```

Parenthesis version:

```python
product_sellrates = (
  shop_prod_compatibility.melt(
    ["shop_id", "item_id", "customer_id", "Shop Name"]
  )
  .dropna()
  .reset_index(drop=True)
)
```

Python does not allow you to break the line at the `=` without using
parenthesis.

> ⚠️
> Adding a trailing comma will make the result of the function call be
wrapped in a tuple instead

An auto-formatter like [`black`][1] would do this automatically.


[1]: https://pypi.org/project/black/

Tags:

    #literature-notes #tips #clean-code #python

