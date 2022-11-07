# cookie_jar_to_dict_cookies
useful if using for selenium\playwright

def cookie_jar_to_dict_cookies(filename):
    cookies = MozillaCookieJar(filename)
    cookies.load(ignore_discard=True, ignore_expires=True)

    cookies_list = []
    for cookie in iter(cookies):
        cookies_list.append({
            "name": cookie.name,
            "value": cookie.value,
            "domain": cookie.domain,
            "path": cookie.path
        })

    return cookies_list
