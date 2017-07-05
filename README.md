## PoGo/PTC Ban Check

Checks proxies or your external IP for bans in PokemonGO and PTC.

### Checking your own IP Address

If you don't use proxies, simply don't create a proxy file.
The script will ask if you'd like to continue with your external IP instead.

### Checking a list of Proxies

Proxies should be stored in proxies.txt (unless you change the `ProxyFile` option) with one proxy per line.

Proxies must be in one of the following formats:
* `protocol://ip:port`
* `protocol://user:password@ip:port`

If you don't specify protocol, curl will normally use HTTP.

#### Output

Proxies are added to a new file based the response received:

* **200**: `proxies_good.txt`
* **403** (PoGo) or **409** (PTC): `proxies_banned.txt`
* All others: `proxies_bad.txt`

You'll have the option to clear the files before it starts.

### Options

#### Timeout
Sets the maximum time curl will wait for a response when checking a proxy.

#### MaxDelay
Upper limit for the random delay between proxy checks.

#### MaxRetries
Number of times to retry if curl gets a timeout or a `5xx` error. Set to 0 to disable.

#### ProxyFile
Change this to load proxies from a different file or directory.


### Misc

If you found this project useful, you're welcome to [buy me a beer](https://paypal.me/GalacticaPogo).

If you're looking for a developer or just want to say thanks, I'm on Discord as **@Galactica#7178**.
