# CRUD operations performed via Django shell


## Create
```py
from bookshelf.models import Book
b = Book.objects.create(title="1984", author="George Orwell", publication_year=1949)
print(b)
# Expected output: 1984 by George Orwell (1949)
```


## Retrieve
```py
from bookshelf.models import Book
books = Book.objects.all()
print(books)
# Expected output: <QuerySet [<Book: 1984 by George Orwell (1949)>]>


book = books.first()
print(book.title, book.author, book.publication_year)
# Expected output: 1984 George Orwell 1949
```


## Update
```py
from bookshelf.models import Book
book = Book.objects.get(title="1984")
book.title = "Nineteen Eighty-Four"
book.save()
print(Book.objects.get(pk=book.pk))
# Expected output: Nineteen Eighty-Four by George Orwell (1949)
```


## Delete
```py
from bookshelf.models import Book
book = Book.objects.get(title="Nineteen Eighty-Four")
book.delete()
# Expected output: (1, {'bookshelf.Book': 1})


print(Book.objects.all())
# Expected output: <QuerySet []>
```