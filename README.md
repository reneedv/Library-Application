Library-Application
===================

Rails Summer Library Application

Things to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

[![Code Climate](https://codeclimate.com/github/Rails-Summer-Project-Noah-and-Matt/Library-Application.png)](https://codeclimate.com/github/Rails-Summer-Project-Noah-and-Matt/Library-Application)


Project Plan: 
  - Build a GIT repo to share with Noah
  - We are going to be strict about testing
  - Failing tests or code w/o tests gets committed to a branch
  - Passing tests get merged to master with an issue number
  - No commits / merges to master w/o issue number

Concerns:
  - Multiple branches could cause issues with DB migrations

Progress Tracking:
  - We'll use GIT issues for Project Tracking

Database Schema:
  - Books
    - Multiple Books can have the same title
    - Book title can have different ISBNs 
    - is_active
    - picture (foreign key to book_covers)
    - owner (foreign key to user_id, for req 5 only edit book you entered)
    - has_many :book_authors
    - has_many :authors, through :book_authors
    - has_many :isbn
    - has_many :book_tags
    - has_many :tags, through :book_tags
    - has_many :reviews (we will pull ratings from the reviews)
  - Book_Covers
    - has_many :books
  - Tags
    - has_many :book_tags
    - has_many :books, through :book_tags
  - Reviews
    - (req 19) Renee - what do you mean by search on review? date, or contents,
      or both, or "figure it out"?
    - book
    - user
    - review
    - ratings (we are temporarily saying this is part of reviews, but 
      it is possible we will want to pull it out)
  - ISBN has many books
  - Authors 
    - first_name
    - last_name
    - has_many :book_authors
    - has_many :books, through :book_authors
  - Users
    - Reviews and Tags, ratings
    - email
    - username
    - is admin ?
    - is_blocked (req 18)
    - email preferences - how to handle - req 11-16 - probably one or more 
      add'l tables
    - ? should we do a hook for "activity", or gen reports as requested?
      (for req 20) - I think as requested.

  Database:
    - SQlite for Dev and Test
    - Postgres for Production

