# Installation

This guide runs the current app locally from a source checkout. The repository
contains one application file, `app.py`, and does not currently include a
`requirements.txt`, `pyproject.toml`, lockfile, or declared minimum Python
version. Python 3 and Streamlit are the only requirements identified by the
current source and README.

## 1. Get the source

Clone the repository and enter its root directory:

```sh
git clone https://github.com/Brajesh31/carbon-calculator.git
cd carbon-calculator
```

If you have already cloned it, update your checkout with `git pull` before
following the steps below.

## 2. Create an isolated Python environment

On Windows PowerShell:

```powershell
py -m venv .venv
.venv\Scripts\Activate.ps1
```

On macOS or Linux:

```sh
python3 -m venv .venv
source .venv/bin/activate
```

An isolated environment keeps this project's Python packages separate from
other projects. The `.venv/` directory is excluded by `.gitignore`.

If PowerShell prevents the activation script from running, you can use the
environment's executables directly instead of changing machine-wide execution
policy:

```powershell
.venv\Scripts\python.exe -m pip install --upgrade pip
.venv\Scripts\python.exe -m pip install streamlit
.venv\Scripts\python.exe -m streamlit run app.py
```

## 3. Install Streamlit

With the environment activated, run:

```sh
python -m pip install --upgrade pip
python -m pip install streamlit
```

The project does not pin a Streamlit version. This command installs the version
available from the configured Python package index at installation time, so
different checkouts may receive different versions. A dependency file with
reviewed, pinned versions should be added before relying on reproducible
deployments.

## 4. Start the app

From the repository root, run:

```sh
streamlit run app.py
```

Streamlit prints the local address in the terminal, typically
`http://localhost:8501`, and may open a browser automatically. Use the page's
**Calculate CO2 Emissions** button to display the estimate. Stop the local
server with `Ctrl+C` in the terminal.

## Configuration and data

The current app does not read environment variables, require API credentials,
or use a database. `.env.example` records this fact. Do not add secrets or
personal data to the repository. For how the application handles widget values
and why the estimates are provisional, see [architecture](architecture.md)
and [database and data handling](database.md).

## Next steps

- For editing and review practices, read [development.md](development.md).
- For hosted deployment considerations, read [deployment.md](deployment.md).
- If startup fails, consult [troubleshooting.md](troubleshooting.md).
