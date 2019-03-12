# Adding_New_Texts_To_OpenITI

Repository to streamline the process of adding new texts to OpenITI

The overall workflow is as follows:

1. Folder `new_texts` can be used to add texts that should be included into OpenITI.
  - users can `fork` this repository and add a text that would like to include into OpenITI into the `new_texts` folder.
  - the text should be assigned an ID, which should be generated in the following manner:
    - `MGR2019031201`, where MGR is the initials of a scholar (here: Maxim G. Romanov), and the numbers are 2019-03-12-01, meaning that the text has been added to the repository at 1am, on the 12th of March, 2019. This structure should allow to add small batches of files. The file should have no extension. **NB:** you can also use the preceding dates, if your batch is large.
    - for each text file a short metadata file should be added (see the description below; you can copy paste the tamplate from there as well). This file should be named with the same ID. E.g., `MGR2019031201`, but an extension `.yml` should be added to it. That is the name of this file would look like `MGR2019031201.yml`).
  - the user then sends a pull request with a short message.
2. The OpenITI team member then:
  - verifies submitted data
  - if a text is approved, a `process: yes` value should be added to its metadata `yml` file
  - the URI might need to be assigned
3. The integration script is executed:
  - the place of the new text is derived from the URIs
  - all required subfolders are created (if necessary)
  - the text file is renamed and copied to the newly created folders
  - the processed text file from the `new_texts` (together with its metadata file) is moved to the `processed_texts` folder.

# Metadata file

## Template for copy/pasting

```
fileID: 
URI:
Language:
Author:
Book:
Manuscript:
BibTitle:
BibPlace:
BibPublisher:
BibEditor:
BibPlace:
BibDate:
```

## An example of how information should be added

- **fileID**. The file ID must be provided
- **URI**. The URI should be suggested, but the field can be left empty.
  - the users should first check whether relevant URIs already exist (either for the author or the book).
  - if the URI does not exist, the users should use the logic described here: <https://maximromanov.github.io/OpenITI/#a-note-on-the-principles-of-assigning-human-readable-uris>
  - if the process seems complicated, the users should just provide information about the author and the book, and the URI will be assigned by the OpenITI team members.
- **Language**. The language of the text (if multiple, separate with commas)
- **Author**. Sufficient description on the author should be added --- use an example below as a guide
- **Book**. Sufficient description on the text should be added --- use an example below as a guide
- **Manuscript.** Fill this one only if your text is your own transcription of a manuscript. add a free-runing description of the manuscript.
- **Bib**-*fields* should include relevant information on the edition, if the text is based on a specific edition.

```
fileID: MGR2019031201
URI: 0748Dhahabi.TarikhIslam
language: Arabic 
Author: (from EI2) al-Ḏh̲ahabī, S̲h̲ams al-Dīn Abū ʿAbd Allāh
    Muḥammad b. ʿUt̲h̲mān b. Ḳāymāẓ b. ʿAbd Allāh al-Turkumānī al-Fāriḳī
    alDimas̲h̲ḳī al-S̲h̲āfiʿī, an Arab historian and theologian, was born at
    Damascus or at Mayyāfariḳīn on 1 or 3 Rabīʿ II (according to al-Kutubī,
    in Rabīʿ I) 673/5 or 7 October 1274, and died at Damascus, according to
    al-Subkī and al-Suyūṭī, in the night of Sunday-Monday on 3 D̲h̲u
    ’l-Ḳaʿda 748/4 February 1348, or, according to Aḥmad b. ʿIyās, in
    753/1352-3. He was buried at the Bāb al-Ṣag̲h̲īr.
Book: (from EI2) His greatest work is the Taʾrīk̲h̲ al-Islām
    (“History of Islam”), printed together with his Ṭabaḳāt al-mas̲h̲āhīr wa
    ’l-aʿlām at Cairo from 1367/1947-6 onwards, an extensive history of
    Islam, beginning with the genealogy of the Prophet Muḥammad and ending
    with the year 700/1300-1. It follows the system of the Kitāb al-muntaẓam
    of Ibn al-Ḏj̲awzī [q.v.], containing both the general narrative ( al-
    ḥawādit̲h̲ al-kāʾina ) and the obituary notices of the persons who died
    in the several years ( al-mutawaffūn ). The whole work is divided into
    “classes” (ṭabaḳāt) of decades, so that it contains seventy “classes”
    altogether. In each decade first comes the general narrative, subdivided
    into the several years; then follow the “classes” of the obituary
    notices, equally subdivided into the several years, and ended by the
    obituary notices of persons whose exact dates of death could not be
    stated. The relation of the extent of the general narrative to that of
    the obituary notices is, on an average, 1 to 6 or 7.
BibTitle: include here the title as it appears in the printed edition ()
BibPlace: place of publication
BibPublisher: publisher and edition number
BibEditor: name of the editor
BibPlace: place of publication
BibDate: year of publication
```

# Repository structure

```
dir: new_texts
dir: processed_texts
fil: processing_script.py
fil: README.md (this file)
```
