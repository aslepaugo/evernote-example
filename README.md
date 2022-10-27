# Evernote API examples

There are set of scripts to demonstarte basic working with [Evernote](https://evernote.com) through API.
Python SDK is available only for Python 2.7.

## Prepare and setup

To use scripts you need Python 2.7 installed on your system.

Install all dependencies:

```shell
pip2 install -r requirements.txt
```

Create `.env` file and setup following keys:

```shell
EVERNOTE_PERSONAL_TOKEN = <>
JOURNAL_TEMPLATE_NOTE_GUID = <>
JOURNAL_NOTEBOOK_GUID = <>
INBOX_NOTEBOOK_GUID = <>
```

All deta and API Key access are available on the [Dev Evernote page] (https://dev.evernote.com/doc/start/python.php).

## Scripts and usage

### list_notebook.py

Get list of Notebooks and GUID (you can use them in `.env` then).

```shell
python2.7 list_notebooks.py

f0b5ec60-ce32-431c-9e47-66c1384a8561 - First Notebook
ffb00b38-7dec-49e8-ab3c-d83b0e2e023e - Second Notebook
```  

### dump_inbox.py

List of notes in Notebook from environment variable `INBOX_NOTEBOOK_GUID`.

```shell
python2.7 dump_inbox.py --help
usage: dump_inbox.py [-h] [number]

Dumps notes from Evernote inbox to console

positional arguments:
  number      number of records to dump

optional arguments:
  -h, --help  show this help message and exit
```

```shell
python2.7 dump_inbox.py

--------- 1 ---------


Note text inside note.
```  

### add_note2journal.py

Add note to defined notebook `JOURNAL_NOTEBOOK_GUID` based on template `JOURNAL_TEMPLATE_NOTE_GUID`.

```shell
python2.7 add_note2journal.py --help
usage: add_note2journal.py [-h] [date]

Adds note to notebook "Дневник", uses template note

positional arguments:
  date        date in format "YYYY-MM-DD"

optional arguments:
  -h, --help  show this help message and exit
```

```shell
python2.7 add_note2journal.py 2022-10-01

Title Context is:
{
    "date": "2022-10-01",
    "dow": "суббота"
}
Note created: Template Note
Done
```

### config.py

Access and define environment variables.
