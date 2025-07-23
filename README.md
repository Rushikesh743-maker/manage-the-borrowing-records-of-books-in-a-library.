# manage-the-borrowing-records-of-books-in-a-library.
library_data = {
    "Member1": ["Python", "Java", "DSA"],
    "Member2": ["DSA", "Java"],
    "Member3": [],
    "Member4": ["Python", "DSA", "C++", "Java"],
}

#Compute the average number of books borrowed by all library members
total_books = sum(len(books) for books in library_data.values())
num_members = len(library_data)
average_borrowed = total_books / num_members if num_members > 0 else 0
print("Average number of books borrowed per member:", average_borrowed)

#Count borrowings of each book
book_count = {}
for books in library_data.values():
    for book in books:
        book_count[book] = book_count.get(book, 0) + 1

# Find highest borrowed book
highest_book = max(book_count, key=book_count.get)
print(f"Most borrowed book: {highest_book} ({book_count[highest_book]} times)")

# Find lowest borrowed book
lowest_book = min(book_count, key=book_count.get)
print(f"Least borrowed book: {lowest_book} ({book_count[lowest_book]} times)")

#Count members who have borrowed 0 books
zero_borrow_members = sum(1 for books in library_data.values() if len(books) == 0)
print("Number of members with 0 borrowed books:", zero_borrow_members)

# Most frequently borrowed book (mode)
most_frequent_book = highest_book  # Same as highest count
print("Most frequently borrowed book (mode):", most_frequent_book)
