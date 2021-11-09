![Visitors](https://visitor-badge.laobi.icu/badge?page_id=Hattorius.Tradingview-ticker)
# Tradingview-ticker
Reverse engineered connection to the TradingView ticker in Python. Makes a websocket connection to the Tradeview website and receives price & volume updates realtime. Developed & tested in Python 3.9.5 (So didn't test others)

## Table of contents
* [Features](#features)
* [Prerequisites](#prerequisites)
* [Installing](#installing)
* [Quick example](#quick-example)
* [Documentation](https://github.com/Hattorius/Tradingview-ticker/wiki/API-Reference)
* [License](#license)

## Features
* Keeps websocket connection alive
* Can watch multiple tickers on the same time
* Doesn't cooldown / ratelimit
* Easy to use
* Stable **ASF** *(it's still running after writing all this stuff so it's good enough for me)*

## Prerequisites
* [Python 3.8+](https://www.python.org/downloads/)

Make sure Python is added to your PATH on Windows, more info [here](https://superuser.com/questions/143119/how-do-i-add-python-to-the-windows-path) if you didn't let it set the PATH at install.

## Installing
Please install the requirements:
```
# Linux/macOS
python3 -m pip install -r requirements.txt

# Windows
py -3 -m pip install -r requirements.txt
```
And then you're ready to run!

## Quick Example
```py
import time
from ticker import ticker

tick = ticker("BINANCE:BTCUSDT")
tick.start()

while (True): # Print out prices & volumes every 2 seconds
    print(tick.states)
    time.sleep(2)
```
### Multiple Symbols
```py
import time
from ticker import ticker

tick = ticker(["BINANCE:BTCUSDT","NASDAQ:AAPL"])
tick.start()

while (True): # Print out prices & volumes every 2 seconds
    print(tick.states)
    time.sleep(2)
```

## License
This project is licensed under the GNU GPLv3 License - see the [LICENSE](LICENSE) file for details. 
