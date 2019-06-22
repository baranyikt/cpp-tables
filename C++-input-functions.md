# C++ standard input functions comparison

| Name | Header | Std | Description | Signature |
| ---- | ------ | --- | ----------- | --------- |
| [getc](https://en.cppreference.com/w/c/io/fgetc) | stdio | C89 | reads single char or EOF(-1) from FILE  | int getc(FILE *stream) |
| [fgetc](https://en.cppreference.com/w/c/io/fgetc) | stdio | C89 | *< same, just guaranteed to not be a macro >* | int fgetc(FILE *stream) |
| [getchar](https://en.cppreference.com/w/c/io/getchar) | stdio | C89 | reads char from stdin but waits for EOL [EOL not extracted!] | int getchar() |
| [getch](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getch?view=vs-2019) | conio | | reads ONE single char from stdin (keyboard) without waiting for EOL | int getch() |
| [getche](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getche?view=vs-2019) | conio | | reads ONE single char from keyboard unbuffered with echo to screen | int getche() |
| [kbhit](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/posix-kbhit?view=vs-2019) | conio | | checks whether keyboard press is waiting in the keyboard buffer returning a bool-like value (non-blocking) | int kbhit() |
| [_getch](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getch-getwch?view=vs-2019) | conio | | *< more ISO compatible names for getch()/getche()/kbhit() >* | int _getch() |
| [_getche](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getche-getwche?view=vs-2019) | conio | | *< though un-underscored version could be more portable, cf. [ncurses](http://www.gnu.org/software/ncurses/ncurses.html) >* | int _getche() |
| [_kbhit](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/kbhit?view=vs-2019) | conio | |  | int _kbhit() |
| [_getchar_nolock](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getchar-nolock-getwchar-nolock?view=vs-2019) | stdio | | "nolock" is for "no protection against interference by other threads" (could be faster a bit) | int _getchar_nolock() |
| [_getch_nolock](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getch-nolock-getwch-nolock?view=vs-2019) | stdio | | "nolock" is for "no protection against interference by other threads" (could be faster a bit) | int _getch_nolock() |
| [_getche_nolock](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getche-nolock-getwche-nolock?view=vs-2019) | stdio | | "nolock" is for "no protection against interference by other threads" (could be faster a bit) | int _getche_nolock() |
||
| [gets](https://en.cppreference.com/w/cpp/io/c/gets) | stdio | C89 | reads chars from stdin into char* until EOL/EOF, regardless of buffer size. **Do not use it**. Removed in C11.| char * gets( char *str ) |
| [gets_s](https://en.cppreference.com/w/c/io/gets) | stdio | C11 | reads chars from stdin into char* until EOL/EOF, bounds-checked version [EOL extracted and dropped, *not* appended] | char * gets_s(char*, rsize_t) |
| [fgets](https://en.cppreference.com/w/c/io/fgets) | stdio | C89 | reads chars from FILE into char* until EOL/EOF (bounds-checked)	[EOL extracted and appended to input] | char * fgets(char*, int count, FILE*) |
| [scanf](https://en.cppreference.com/w/c/io/fscanf) | stdio | C89 | reads formatted from stdin [strings are delimited by any whitespace, which are not extracted and not appended] | int scanf(const char* format, ... ) |
| [fscanf](https://en.cppreference.com/w/c/io/fscanf) | stdio | C89 | reads formatted from FILE | int fscanf(FILE*, const char* format, ... ) |
| [sscanf](https://en.cppreference.com/w/c/io/fscanf) | stdio | C89 | reads formatted from char* | int sscanf(const char * buffer, const char * format, ... ) |
| [scanf_s](https://en.cppreference.com/w/c/io/fscanf) | stdio | C11 | *< bounds-checked versions of the above three >* | |
| [fscanf_s](https://en.cppreference.com/w/c/io/fscanf) | stdio | C11 | ||
| [sscanf_s](https://en.cppreference.com/w/c/io/fscanf) | stdio | C11 | ||
| [getline](https://en.cppreference.com/w/c/experimental/dynamic/getline) | stdio | DM:TR | allocates/reallocates char** according to the size of chars to read (autogrow) [EOL extracted & appended] | ssize_t getline(char**, size_t*, FILE*) [[like a reallocating fgets()]] |
| [getdelim](https://en.cppreference.com/w/c/experimental/dynamic/getline) | stdio | DM:TR | *< same as getline, just delimiter can be chosen >* | ssize_t getdelim(char**, size_t*, int delimiter, FILE*) |
| [istream::peek](https://en.cppreference.com/w/cpp/io/basic_istream/peek) | istream | C++98 | reads one char from stream if possible without extracting it (or returns EOF), called with cin: waits for EOL like getchar() | int istream::peek() |
| [istream::ignore](https://en.cppreference.com/w/cpp/io/basic_istream/ignore) | istream | C++98 | extracts and discards characters from stream | istream& ignore( std::streamsize count = 1, int_type delim = Traits::eof() ) |
| [istream::get](https://en.cppreference.com/w/cpp/io/basic_istream/get) | istream | C++98 | reads one char from stream if possible [[like getc()]] | int istream::get() |
| [istream::get(char&)](https://en.cppreference.com/w/cpp/io/basic_istream/get) | istream | C++98 | reads one char into arg if possible | istream& istream::get(char_type&) |
| [istream::get(char*, count)](https://en.cppreference.com/w/cpp/io/basic_istream/get) | istream | C++98 | reads char* until EOL/EOF bounds-checked [EOL not extracted] | istream& istream::get(char_type*, std::streamsize [, char_type delim]) |
| [istream::getline(char*, count)](https://en.cppreference.com/w/cpp/io/basic_istream/getline) | istream | C++98 | reads char* until EOL/EOF bounds-checked [EOL extracted and dropped] | istream& istream::getline(char_type*, std::streamsize count [, char_type delim]) |
| [std::getline(istream, string)](https://en.cppreference.com/w/cpp/string/basic_string/getline) | string | C++98/11 | reads string until EOL/EOF autogrow [EOL extracted and dropped] | istream& std::getline(istream&[&] stream, string& str [, char_type delim]) |
||
| [istream::read](https://en.cppreference.com/w/cpp/io/basic_istream/read) | istream | C++98 | reads buffer from stream | 
| [istream::readsome](https://en.cppreference.com/w/cpp/io/basic_istream/readsome) | istream | C++98 | read at most N characters, but stops at the end of internal buffer (see also [this](http://www.cplusplus.com/reference/istream/istream/readsome/) ) | std::streamsize istream::readsome( char_type* s, std::streamsize count ) |
| [cin.read(char*,1)](https://en.cppreference.com/w/cpp/io/basic_istream/read) | istream | C++98 | reads one character, waits for EOL [EOL not extracted!] (basically a getc()/getchar() for streams) | |
| [cin.read(char*,N)](https://en.cppreference.com/w/cpp/io/basic_istream/read) | istream | C++98 | reads N characters |
||
| [istream::operator>>(datatype&)](https://en.cppreference.com/w/cpp/io/basic_istream/operator_gtgt) | istream | C++98 | reads formatted from stream, datatype can be bool, [unsigned] short/int/long/long long, float, [long] double, void* | istream& operator>> (datatype& val) |
| [istream::operator>>(streambuf&[, char_type delim])](https://en.cppreference.com/w/cpp/io/basic_istream/operator_gtgt) | istream | C++98 | reads all available data (or data up to delim) to another stream | istream& operator>>( std::basic_streambuf<char_type,Traits>* sb ) |

Notes: 

1)
- istream stands for std::basic_istream<char_type,Traits> everywhere, and
- string is for std::basic_string<char_type>

2) This also means that for stream functions above the widechar (wchar_t) equivalents are the same, only instantiated with char_type=wchar_t instead of char_type=char.

3) ssize_t and std::streamsize can be thought to be the same, and the same stands for rsize_t and size_t also.

4) 
- C_DM_TR:	ISO C Dynamic Memory TR extensions: available if \__STDC_ALLOC_LIB__, and then can be switched ON using \__STDC_WANT_LIB_EXT2__ 1 before #include <cstdio>
- C_BOUNDS:	Bounds checked extensions: available if \__STDC_LIB_EXT1__, and than can be switched ON using \__STDC_WANT_LIB_EXT1__ 1 before #include <cstdio>

5) std::istream::operator>> functions have their [std namespace function template versions](https://en.cppreference.com/w/cpp/io/basic_istream/operator_gtgt2) (std::operator>>) too

## End-Of-Line extraction

| fn           |     EOL       | input | output | std | header |
| ------------ | ------------- | ----- | ------ | --- | ------ |
| getchar      | left          | stdin | int    | C89 | stdio  |
| scanf        | left          | stdin | char*  | C89 | stdio |
| fscanf       | left          | FILE  | char*  | C89 | stdio |
| istream::get(char*) | left   | stream | char* | C++98 | istream |
| gets[_s]     | dropped       | stdin | char*  | C89/11 | stdio |
| istream::getline(char*) | dropped | stream | char* | C++98 | istream |
| std::getline | dropped       | stream | string | C++98 | string |
| fgets        | appended      | FILE  | char*  | C89 | stdio |
| getline DM   | appended      | FILE  | char*  | DM:TR | stdio |

## Widechar-equivalents (for non-stream functions)

| function       | widechar-equiv. | header | 
| -------------- | --------------- | ------ |
| [getc/fgetc](https://en.cppreference.com/w/c/io/fgetc) | [fgetwc](https://en.cppreference.com/w/cpp/io/c/fgetwc) | wchar |
| [getchar](https://en.cppreference.com/w/c/io/getchar) | [getwchar](https://en.cppreference.com/w/cpp/io/c/getwchar) | wchar |
| [_getch](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getch-getwch?view=vs-2019) | [_getwch](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getch-getwch?view=vs-2019) | conio or wchar |
| [_getche](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getche-getwche?view=vs-2019) | [_getwche](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getche-getwche?view=vs-2019) | conio or wchar |
| [_getchar_nolock](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getchar-nolock-getwchar-nolock?view=vs-2019) ... | [_getwchar_nolock](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/getchar-nolock-getwchar-nolock?view=vs-2019) ... | stdio or wchar |
| [gets_s](https://en.cppreference.com/w/c/io/gets) | [_getws_s](https://docs.microsoft.com/en-us/cpp/c-runtime-library/reference/gets-s-getws-s?view=vs-2019) | stdio or wchar |
| [fgets](https://en.cppreference.com/w/c/io/fgets) | [fgetws](https://en.cppreference.com/w/cpp/io/c/fgetws) | wchar |
| [scanf/fscanf/sscanf](https://en.cppreference.com/w/c/io/fscanf) | [wscanf, fwscanf, swscanf](https://en.cppreference.com/w/c/io/fwscanf) | wchar |
| [scanf_s/fscanf_s/sscanf_s](https://en.cppreference.com/w/c/io/fscanf) | [wscanf_s, fwscanf_s, swscanf_s](https://en.cppreference.com/w/c/io/fwscanf) | wchar |
| [getline](https://en.cppreference.com/w/c/experimental/dynamic/getline) | [getwline](https://en.cppreference.com/w/c/experimental/dynamic/getline) | stdio |
| [detdelim](https://en.cppreference.com/w/c/experimental/dynamic/getline) | [getwdelim](https://en.cppreference.com/w/c/experimental/dynamic/getline) | stdio |

Links:

[ see Notes section in https://en.cppreference.com/w/cpp/string/basic_string/getline ]

[ https://en.cppreference.com/w/c/experimental/dynamic ]

[ https://stackoverflow.com/questions/12008979/differences-between-getch-and-getch ]

[ https://stackoverflow.com/questions/814975/getch-is-deprecated ]

[ https://docs.microsoft.com/en-us/cpp/error-messages/compiler-warnings/compiler-warning-level-3-c4996?view=vs-2019 ]

[ https://www.geeksforgeeks.org/difference-getchar-getch-getc-getche/ ]

[ C++ named requirements:UnformattedInputFunction https://en.cppreference.com/w/cpp/named_req/UnformattedInputFunction ]

[ C++ named requirements:FormattedInputFunction https://en.cppreference.com/w/cpp/named_req/FormattedInputFunction ]

