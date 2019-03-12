# Adding_New_Texts_To_OpenITI

Repository to streamline the process of adding new texts to OpenITI

The overall workflow is as follows:

1. Folder `new_texts` can be used to add texts that should be included into OpenITI.
  - users can `fork` this repository and add a text that would like to include into OpenITI into the `new_texts` folder.
  - the text should be assigned an ID, whouch should be generated in the following manner:
    - `MGR2019031201`, where MGR is the initials of a scholar (here: Maxim G. Romanov), and the numbers are 2019-03-12-01, meaning that the text has been added to the repository at 1am, on the 12th of March, 2019. This structure should allow to add small batches of files. The file should have no extension. **NB:** you can also use the preceding dates, if your batch is large.
    - for each text file a short metadata file should be added (copy-paste from below)
  - they then send a pull request, where they suggest a URI for their new texts.
    - the users should first check whether relevant URIs already exist (either for the author or the book).
    - if the URI does not exist, the users should use the logic described here: <https://maximromanov.github.io/OpenITI/#a-note-on-the-principles-of-assigning-human-readable-uris>
    - if the process seems complicated, the users should just provide information about the author and the book, and the URI will be assigned by the OpenITI team members.
    



# Metadata file

## Template for copy/pasting

```
fileID: 
URI:
Author:
Book:
```

## An example of how information should be added

```
fileID: 
URI:
Author:
Book:
```
