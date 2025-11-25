## Delete
```py
from bookshelf.models import Book
book = Book.objects.get(title="Nineteen Eighty-Four")
book.delete()
# Expected output: (1, {'bookshelf.Book': 1})


print(Book.objects.all())
# Expected output: <QuerySet []>
```