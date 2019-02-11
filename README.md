# hdr10plus_parser [![Travis Build Status](https://travis-ci.org/quietvoid/hdr10plus_parser.svg?branch=master)](https://travis-ci.org/quietvoid/hdr10plus_parser) [![AppVeyor Build Status](https://ci.appveyor.com/api/projects/status/github/quietvoid/hdr10plus_parser?branch=master&svg=true)](https://ci.appveyor.com/project/quietvoid/hdr10plus_parser/history)

Tool to check if a HEVC file contains SMPTE 2094-40 metadata in SEI 
messages.

If dynamic metadata is found, the whole file is parsed through and a 
metadata JSON file is generated for use with x265/other encoders.

# Usage, in CLI:

* hdr10plus_parser.exe "path/to/file.hevc"
* ffmpeg -i "input.mkv" -c:v copy -vbsf hevc_mp4toannexb -f hevc - | hdr10plus_parser.exe -

options:
* -i, --input <INPUT> Sets the input file to use.
* -o, --output <OUTPUT> Sets the output JSON file to use.

* --verify  Checks for dynamic metadata only.

# Sample files
Tears of Steel samples encoded with x265 using --dhdr10-info for tests.

Sample JSON metadata available here: https://bitbucket.org/multicoreware/x265/downloads/

# Windows builds
Automated Windows builds can be found on [AppVeyor](https://ci.appveyor.com/project/quietvoid/hdr10plus-parser/history). Select the most recent build from the master branch, where hdr10plus_parser.exe will be available under the artifacts tab.
