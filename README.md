# sgp4-test-data

This repository contains a large JSON file with sgp4 test data.

The source is https://github.com/shashwatak/satellite-js/blob/1d52cbae62e20a6388e0ea3a01c5cc9590609050/test/propagation/__snapshots__/sgp4Catalog.test.js.snap

There are 128313 test cases. Each test case is structured as follows:

```json
    {
        "norad": 12,
        "tle": {
            "line1": "1    12U 59001B   22221.44187552  .00000108  00000-0  41309-4 0  9993",
            "line2": "2    12  32.9087 130.8390 1665650 233.4456 110.1176 11.44690528612279"
        },
        "epoch_utc": "2022-08-09T10:36:18.045Z",
        "t_min_since_epoch": 0,
        "position": {
            "x": -5869.9169277202145,
            "y": 6791.004588475254,
            "z": 0.0037576740924038414
        },
        "velocity": {
            "x": -4.630159774803886,
            "y": -2.7654049420795106,
            "z": 3.4389423149777203
        }
    },
```

The test procedure is to
- load the TLE
- propagate the orbit to `t_min_since_epoch`
- compare the position and velocity with the expected values
