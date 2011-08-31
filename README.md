# HTTP cURL Requests for Humans

Curl requests for Humans


## Features:

- Custom HTTP headers
- Request data/params
- Multiple file uploading
- Cookies support (dict or CookieJar)
- Redirection history
- Proxy support (http, https, socks4/5)
- Custom interface for request!
- Auto decompression of GZipped content
- Unicode URL support
- Request timers and another info
- Certificate validation
- ipv6 support


## USAGE

### Simple get request

    >>> import human_curl as requests # python-requests.org compatibile
    >>> r = requests.get('http://h.wrttn.me/basic-auth/test_username/test_password', auth=('test_username', 'test_password'))
    >>> r.status_code
    200
    >>> r.content
    '{"username": "test_username", "password": "test_password", "authenticated": true}'


### Send files and variables

    >>> import human_curl as requests
    >>> r = requests.post('http://h.wrttn.me', files=(('file_1', '/tmp/testfile1.txt'),
    ... ('file2', open('/tmp/testfile2.txt'))), data={'var\_name': 'var\_value'})
	...
    >>> r.status_code
    201


### Redirects

    >>> import human_curl as requests
    >>> r = requests.get('http://h.wrttn.me/redirect/4', allow_redirects=True)
    >>> r.status_code
    200
    >>> print(r.history)
	['http://h.wrttn.me/redirect/3', 'http://h.wrttn.me/redirect/2', 'http://h.wrttn.me/redirect/1', 'http://h.wrttn.me/redirect/end']
    >>> print(r.url)
	http://h.wrttn.me/redirect/end


## TODO

- async client
- curl command generation?


## INSTALLATION

To use human\_curl  use pip or easy\_install:

`pip install human_curl`

or

`easy_install human_curl`


## CONTRIBUTE
Fork https://github.com/Lispython/human_curl/ , create commit, create pull request.

