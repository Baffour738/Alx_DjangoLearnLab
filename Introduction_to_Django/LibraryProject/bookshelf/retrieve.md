## Retrieve
```py
from bookshelf.models import Book
books = Book.objects.get(id = 1)
print(books)
# Expected output: <QuerySet [<Book: 1984 by George Orwell (1949)>]>


book = books.first()
print(book.title, book.author, book.publication_year)
# Expected output: 1984 George Orwell 1949
```