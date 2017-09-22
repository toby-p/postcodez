# postcodez
Python module for managing badly formatted UK postcode data.

The function takes a postcode in any format, and if it is a valid UK postcode returns it in the propert format, with the additional information of Longitude, Latitude, and London Borough (if applicable).

### Installation

Now available to install via pypi:

```
pip install -U postcodez
```
The installation includes ~39Mb of files with the valid UK postcode data.

### Example 1 - valid London postcode in bad format (no spaces, lower case)
```python
postcodez("n146bb")
```
Returns:
```json
{"latitude": 51.638471184099998,
 "london_borough": "Enfield",
 "longitude": -0.117084777613,
 "postcode_IN": "n146bb",
 "postcode_OUT": "N14 6BB"}
 ```
 
 ### Example 2 - badly formatted non-London postcode (no spaces, lower case)
```python
postcodez("s11aa")
```
Returns:
```json
{"latitude": 53.381549394899999,
 "london_borough": "",
 "longitude": -1.4642950000000001,
 "postcode_IN": "s11aa",
 "postcode_OUT": "S1 1AA"}
 ```
 
 ### Example 3 - not a postcode
```python
postcodez("not a postcode")
```
Returns:
```json
{"latitude": "",
 "london_borough": "",
 "longitude": "",
 "postcode_IN": "not a postcode",
 "postcode_OUT": ""}
 ```
