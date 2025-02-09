# `vja-review`

`vja-review` is a python wrapper around [`vja`](https://gitlab.com/ce72/vja), a
command line tool for interacting with [`Vikunja`](https://vikunja.io/). Its
goal it to offer an easy way of reviewing tasks that are either overdue, or are
in a given range (e.g., today's or this week's tasks).

## Installation

Assuming you have a recent version of [`uv`](https://github.com/astral-sh/uv)
installed, you should be able to clone this repo and just run the `vja-review`
script. `uv` will take care of installing the python dependencies.

## Usage

On the first run of the script you 'll get the following error prompting you to
setup the necessary configuration to communicate with Vikunja (namely, providing
a URL, a username and a password)

```
You're not currently logged in to vikunja. Please follow the instructions on this page to login with vja (run it either via `uv run vja` or by directly running vja - depending on how you executed `vja-review`: https://pypi.org/project/vja/
```

After setting it up, you should be able to run the script without any issues.

```
$ ./vja-review --overdue

18:04:07 INFO - Running command: ['vja', 'tasks', 'ls', '--json', '--due-date', 'lt 20250209T180407']
18:04:07 INFO - Found 8 tasks
1/8. Task 277
-------------
Title: Take out the garbage

Due Date: 2025-02-09T12:23:35+02:00
Project ID: 9
Priority: 4
Created: 2025-01-12T16:44:44+02:00
Updated: 2025-02-06T12:23:35+02:00

Options
-------
1. Skip
2. Complete
3. Move To Today
4. Move To Next 7 Days
5. Move To Coming Monday Morning
6. Move To Next 30 Days
7. Move Sometime This Year
```

> [!NOTE]
> The script will prompt you to choose an action and once it received the
> numeric input it will proceed immediately with showing you the next task,
> without waiting for you to press enter.
