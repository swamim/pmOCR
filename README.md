# pmOCR (poor man's OCR service)

A service wrapper for ABBYY OCR LINUX CLIENT (abbyyocr11 www.ocr4linux.com) or maybe other OCR tools that monitors directories and launches a OCR conversion whenever a new file enters.
Basically it's written to monitor up to 4 directories, each producing a different output format (PDF, Word, Excel & CSV).
There's also an option to avoid passing PDFs to the OCR engine that already contain text.

Use install.sh script or copy pmocr.sh to /usr/local/bin and pmocr-srv to /etc/init.d
After installation, please configure /usr/local/bin/pmocr.sh script variables in order to monitor the directories you need.

Launch service (initV style)
service pmocr-srv start

Launch service (systemd style)
systemctl start pmocr-srv

Check service state (initV style)
service pmocr-srv status

Check service state (systemd style)
systemctl status pmocr-srv

## Support for Abbyy OCR Engine linux CLI

Has been tested so far with ABBYY FineReader Engine 11 CLI for Linux releases R2 (v 11.1.6.562411) and R3 (v 11.1.9.622165) but should virtually work with anything as long you adjust the parameters.

## Troubleshooting

Please check pmocr.log file for errors
Filenames containing special characters should work, nevertheless, if your file doesn't work, try to rename it and copy it again to the monitored directory.
