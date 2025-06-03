## Patrón Singleton
Se implementó en `productos/utils.py` para garantizar una única instancia de conexión a la base de datos. Cada vez que se llama a `DatabaseManager()`, se devuelve la misma instancia (verificable con `id()`).

```python
class DatabaseManager:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance