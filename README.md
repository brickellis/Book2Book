# Book2Book
-------
Functionality
-------

This jupyter notebook creates bilingual ebooks (specifically for kindle) for language learners to read a text and its translation at the same time in two, synced columns.

-------
How it Works
-------
Using the multilingual text embedding model, 'distiluse-base-multilingual-cased-v1', the program splits the texts up, vectorizes the substrings, and syncs them to each other from best matches to worst until the whole text is synced up. The jupyter notebook is commented to assist with understanding.This jupyter notebook creates bilingual ebooks (specifically for kindle) for language learners to read a text and its translation at the same time in two, synced columns. Note that the texts will be very closely synced, but some obstacles of the technology prevent a perfect sync. 

1. A translation often adds, moves, or rearranges portions of the original text.
2. While the vectors will be synced, the substrings won't be cut exactly the same way between the texts. Thus, a portion of a given substring may be present in the previous or following substring of its synced counterpart. As an example, in the below image, 'Teacher!” he fell' in the third split is present in the beginning of the fourth split in the Russian version, «Учитель! — повергся он»

-------
How to Use
-------
Open the jupyter notebook in a folder with the two texts you want synced. The source should be titled, [file_name]_source.txt. The translation should be titled, [file_name]_translation.txt. The two outputs will be [file_name].txt for the rigid version of the book and [file_name].html for the dynamic, kindle-compatible, version of the book. Examples for The Brothers Karamazov and its public domain translation are included in the repo. Here is an example of how the html version displays on kindle.

The first cell of the jupyter notebook includes the following, editable, parameters:

File name

file_name = 'karamazov'

Max length a synced up string can be (in characters)

max_chunk_size = 300

Width of a column in the .txt (in characters)

col_width = 22

Spacing between the two columns in the .txt (in characters)

col_spacing = 5

<img width="462" alt="Screenshot 2023-10-12 at 12 19 04 PM" src="https://github.com/brickellis/Book2Book/assets/7196734/8c4a0e13-d23a-4d69-bd82-2038a04b91ba">



-------
Potential Future Updates/Welcome Pull Requests
-------
Optionally include [file_name]_table_of_contents.txt, which will include the chapter headings to split on. This would add chapters to the ebooks as well as give cleaner locations to end the html tables on for rendering purposes.

Have the code adjust the final indices in order to make the substrings more similar (eg Move each index to the index with the nearest sentence-ending punctuation.)
