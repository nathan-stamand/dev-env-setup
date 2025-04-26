# Ansible Virtual Environment

This is probably all common knowledge when working with Python, but I don't really use Python, so...here we are.

## Create .venv

Our zsh hook looks for virtual environment directories that are named `.venv`, so we start by creating that.

```bash
python -m venv .venv # Run this from your directory, otherwise update .venv to be the full path!
```

## Verify that zsh hook is working, or alternatively manually handle the virtual environment

When you `cd` into the directory, assuming the `.zsh_functions` are set up to autoload, you should see a message
confirming the virtual environment was loaded. You should also see it get deactivated when you `cd` out of the directory.

If you don't have this set up anymore for whatever reason, you can manually handle it by running the following when you enter 
the directory with .venv:

```bash
source .venv/bin/activate
```

...And run this when you're ready to exit the virtual environment:

```bash
deactivate # from the directory you're in, probably, although since we've sourced it, idrk
```

## While you're using the virtual environment, install dependencies!

To fully install all packages within the virtual environment, after you've activated the environment run this guy:

```bash
pip install -r requirements.txt
```

And use this to update the `requirements.txt` file with any _new_ packages you may install, so they can be saved in 
a new version of the file:

```bash
pip freeze > requirements.txt
```