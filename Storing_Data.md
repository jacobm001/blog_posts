**Author: Jacob Mastel**

**Suggested Tags:** raspberrypi

# Storing Information on a Raspberry Pi

No matter what you do with your Raspberry Pi, you're bound to need to save information in some way or another. The main site has seen no shortage of questions on [databases](http://raspberrypi.stackexchange.com/search?q=databases) of various types. In this post, I'm going to discuss the various ways to store information on a Raspberry Pi, and the pros and cons of the various options.

## Flat File

### Definition

The simplest method of storing information is in what's called a *[flat file database](https://en.wikipedia.org/wiki/Flat_file_database)*. In short, a flat file database is a set of information that's written entirely to the file system as either a text or binary file. By definition, the entirety of the database is stored in a single file, though many people also refer to a set of files as a flat file database.

Of all the ways you could store information, flat files are usually one of the fastest out there. Since there is no server process involved, your biggest overhead usually comes from whatever library you may be using to save your information. If you're using a binary format, saving to a flat file usually just involves writing your object(s) directly, and if parsing the information into a text format, it's likely your language may have a native library built into it.

There are however, a few major downsides to using a flat file database. The primary being that they don't give you anything in the realm of querying capability. Search or logic that you'd normally get from a database will have to be implemented in your own code. While that's not a downside for many applications, it's a bigger draw back in others.

The other major drawback of using a flat file database is that only one process can use it at a given time, and they are not thread-safe without some kind of custom built mechanism.

### Examples

1. The original Microsoft Word format `.doc` was a binary file where the application simply wrote the document struct using a system `write()` call.
2. A text file containing data parsed as `xml`, `json`, `csv`, or a number of other formats. 

## Embedded Databases

Embedded databases are technically flat file databases. I have, however, separated them into a separate category. Generally speaking, an embedded database is saved as a flat, binary file, and does not require a separate process to manage it.

What differentiates them from a standard flat file database is that the libraries used to interact with them provide a significant subset of the features found in full database management systems (DMS). SQLite for example allows for standard SQL queries, indexing, view creating, and multiprocessing support, among other things.

As a flat file system, you still have a low overhead as it lacks the management process found with a full DMS. Their added functionality does add some overhead, but it's insignificant in comparison.

### Examples

1. [SQLite](http://sqlite.org/) an embedded, relational database
2. [Unqlite](https://unqlite.org/) an embedded, noSQL, document store database

## Database Management Systems

### Examples

### Benefits

### Drawbacks

 