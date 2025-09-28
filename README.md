# Google forms
This is a Python library that provides convenient and efficient interaction with Google Forms. It offers functionalities to retrieve all the questions from a Google Form and submit responses programmatically. With this package, You can seamlessly integrate Google Forms into Your applications and automate form submission processes.

For now only these types of questions are supported:
- multiple choice question
- text answer questions
    - short answer question
    - paragraph question
- dropdown question
- checkboxes question
- dropdown question
- linear scale question
- grid question

## Instalation:
```console
$ git clone https://github.com/piotr-ginal/google-forms.git
$ cd google-forms
$ python -m pip install -e .
```

## Spammers

`spamform` is a CLI tool that enables users to send multiple responses to any Google Form.

### Usage

```console
spamform [OPTIONS] FORM_ID
```

- `FORM_ID`: The ID of the Google Form to interact with (required).
- `--random`: Use random answers for the form.
- `--responses INTEGER`: Number of responses to submit. [default: 1]
- `--workers INTEGER`: Number of worker threads to use. [default: 25]
- `--help`: Show help message and exit.

**Typical usage flow:**

1. Provide the Google Form ID as an argument.
2. When not using `--random`: Answer each question on the form when prompted.
3. Optionally provide the number of replies you want to send (e.g., `--responses 500`).

**Example:**

Result of running the tool:
![cli screenshot](.assets/threaded_spammer_interface.png)

Result in Google Forms dashboard:
![results in google forms dashboard](.assets/google_forms_dashboard_screenshot.png)

Please note that the threaded_spammer_1.py script currently supports the following types of questions:
- text answer questions (short answer question and paragraph question)
- dropdown question
- multiple choice question
- checkboxes question

If your form contains an unsupported question the script will stop. Please remember that if the forms creator disabled multiple answers per user the script wont work.
