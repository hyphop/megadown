[![Build Status](https://travis-ci.com/hyphop/megadown.svg?branch=master)](https://travis-ci.com/hyphop/megadown)

# megadown

Bash script for download files from mega.nz and megacrypter

## Features:

 * /#!, /#N!, mega://enc?, mega://enc2 and ANY megacrypter clon link supported
 * Resume previous downloads
 * MC password protected links supported
 * Download files from list
 * Speed limit

## Dependencies:

 * Bash >= 3
 * OpenSSL with support for AES 128 CTR and AES 128/256 CBC (crypto stuff)
 * python >= 2.6 (JSON parsing and MC password protected links)
 * wget/curl (downloading (curl is preferred if it's present))
 * pv (monitor the progress of data)

## Usage:

```bash
Single url mode:            megadown ['URL'] [OPTION]...

	Options explanation:
	-o,	--output FILE_NAME    Store file with this name (.
	-s,	--speed SPEED         Download speed limit (500b, 500k, 2m).
	-p,	--password PASSWORD   Password for MegaCrypter links.
	-q,     --quiet               Quiet mode.
        -m,     --metadata            Prints file metadata and exits. (File name is base64 encoded).

Multi url mode:             megadown [-l URL_LIST_FILE] [OPTION]...

	Options explanation:
	-s,     --speed SPEED         Download speed limit (integer values: 500B, 500K, 2M).
        -p,     --password PASSWORD   Password for MegaCrypter links (same for every link in a list).
        -q,     --quiet               Quiet mode.
        -m,     --metadata            Prints file metadata and exits. (File name is base64 encoded).
        File line format:          URL [optional_file_name]

```
## Examples

    megadown -l mega_link_list.example
