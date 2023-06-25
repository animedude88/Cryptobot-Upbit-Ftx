# Cryptobot-Upbit-Ftx
A crypto bot to trade using the price difference in Upbit and FTX

Uses a bollinger band indicator with a period of 5 days and standard deviation multiple of 1.3, setting the standard deviation as:
if std<0.006:
  std = 0.006
if std>0.01:
  std = 0.01
std += 0.0015
which worked the best, for an index of (Ftx crypto price) / (Upbit Crypto price) * 1304.

Short positioning and leveraging only works in Ftx so entering a position would only happen when the index touches the upper bollinger band. (Leveraging used to increase the ratio of profit to asset)

When the index touches the upper bollinger band, it indicates that the crypto price in Ftx is relatively more expensive than the price in Upbit => Enter a 2 times short position in Ftx and long position in Upbit

When the index touches the lower bollinger band, it indicates that the crypto price in Upbit is relatively more expensive than the price in Ftx => Close both positions in Ftx and Upbit and equalize the assets in both platform
