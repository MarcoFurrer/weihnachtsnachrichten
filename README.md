# weihnachtsnachrichten

A small collection of Jupyter notebooks and example data to create and (optionally) send personalized Christmas / holiday messages.

This repository contains helpers to generate message text for contacts and an example CSV (`sample_output.csv`) that can be used with a sending workflow (for example, via an API or SMS gateway). The notebooks are intentionally minimal and meant as a starting point you can adapt to your preferred sending method and privacy rules.

## Repository contents

- `make_messages.ipynb` — Notebook to create personalized messages (templates, batching, translations).
- `send_messages.ipynb` — Notebook demonstrating how messages could be sent. It does not contain production credentials — configure your own SMTP/API provider inside the notebook before sending.
- `sample_output.csv` — Example CSV with columns used by the sending notebook. See below for the format.
- `LICENSE` — This project is licensed under the MIT License.

## Quick start

1. Install prerequisites (Python 3.8+ recommended) and Jupyter if you don't already have it. A minimal set of packages you may need are `pandas` and `jupyter`.

2. Open `make_messages.ipynb` in Jupyter or JupyterLab and follow the steps to generate your personalized messages. The notebook produces a CSV similar to `sample_output.csv`.

3. Inspect `sample_output.csv` to confirm the format and sample messages.

4. If you plan to actually send messages, open `send_messages.ipynb` and fill in your sending configuration (SMTP server, API key, or gateway). Do not commit credentials to this repo.

## CSV format

The example `sample_output.csv` contains the following columns (header names present in the file):

- `Given Name` — recipient given name
- `Family Name` — recipient family name
- `Phone 1 - Value` — recipient phone number in international format (E.164 recommended)
- `Text` — the message text to send to that recipient

Example rows are included in the repository. The notebook `send_messages.ipynb` expects the CSV to follow the same header names.

## Security & privacy

- This repository includes example phone numbers and message text only. When you run sending code, ensure you comply with applicable laws and consent requirements for messaging (e.g., GDPR, TCPA).
- Never store real credentials or API keys in the repository. Use environment variables, local config files excluded via `.gitignore`, or a secrets manager.

## Customization

- Templates: Edit the message templates in `make_messages.ipynb` to change tone, language, or variables.
- Sending backend: Replace the sending example with your provider's API (Twilio, MessageBird, SMTP gateways, etc.). The `send_messages.ipynb` notebook includes a sketch that is easy to swap out.

## Contributing

If you'd like to contribute improvements (better templates, tests, or additional notebook examples), please open an issue or a pull request. Keep changes small and document any new dependencies.

## License

This project is provided under the terms of the MIT License — see the `LICENSE` file for details.

## Contact

Maintainer: Marco Furrer

If you have questions about usage or want help adapting the notebooks to a specific sending provider, open an issue or contact the maintainer.
