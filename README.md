
# httplib

Simple, asynchronous, dependency-free, strictly-typed, fully docstringed HTTP server framework.

## Example

```py
from typing import Any
import httplib as app

@app.route('/')
async def index() -> Any:
    return app.template('static/index.html')

@app.route('/hello/<name>')
async def hello(name: str) -> Any:
    return f'<h1>Hello, {name}!'

@app.error(404)
async def not_found() -> Any:
    return await app.template('static/404.html')

app.serve('localhost')

```
