# manage-the-borrowing-records-of-books-in-a-library.
# Library data: 5 members and the books they borrowed
library_data = {
    "Member1": ["Python", "Java", "DSA"],
    "Member2": ["DSA", "Java"],
    "Member3": ["C++"],
    "Member4": ["Python", "DSA", "C++", "Java"],
    "Member5": []
}

# 1. Average number of books borrowed by all members
total_books = 0
for books in library_data.values():
    total_books += len(books)

average = total_books / len(library_data)
print("Average number of books borrowed per member:", average)

# 2. Count how many times each book is borrowed
book_count = {}
for books in library_data.values():
    for book in books:
        if book in book_count:
            book_count[book] += 1
        else:
            book_count[book] = 1

print("\nBook borrow counts:")
for book, count in book_count.items():
    print(f"{book}: {count} times")

# 3. Find the most and least borrowed books
most_borrowed = max(book_count, key=book_count.get)
least_borrowed = min(book_count, key=book_count.get)
print("\nMost borrowed book:", most_borrowed, "(", book_count[most_borrowed], "times )")
print("Least borrowed book:", least_borrowed, "(", book_count[least_borrowed], "times )")

# 4. Count members who borrowed 0 books
zero_borrow_members = 0
for books in library_data.values():
    if len(books) == 0:
        zero_borrow_members += 1
print("\nNumber of members who borrowed 0 books:", zero_borrow_members)

# 5. Most frequently borrowed book (mode)
print("Most frequently borrowed book:", most_borrowed)

