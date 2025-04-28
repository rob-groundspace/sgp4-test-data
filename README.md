# sgp4-test-data

This repository contains a large JSON file with sgp4 test data.

The source is https://github.com/shashwatak/satellite-js/blob/1d52cbae62e20a6388e0ea3a01c5cc9590609050/test/propagation/__snapshots__/sgp4Catalog.test.js.snap

There are 128313 test cases. Each test case is structured as follows:

```json
    {
        "tle": [
            "1    12U 59001B   22221.44187552  .00000108  00000-0  41309-4 0  9993",
            "2    12  32.9087 130.8390 1665650 233.4456 110.1176 11.44690528612279"
        ],
        "exp": [
            "0 -5869.91692772 6791.00458848 0.00375767 -4.630159775 -2.765404942 3.438942315",
            "360 227.52361736 7184.90026295 -3097.78777973 -6.558370811 2.422818275 2.247491926",
            "720 5721.78463796 1731.24600739 -3578.63260559 -2.885514837 7.458268123 -1.594529993",
            "1080 4878.63225444 -5497.39406524 -279.77992872 4.125162794 5.122964578 -4.15046689",
            "1440 -910.50115014 -7711.81908924 3493.64506371 6.090516856 -0.775240884 -2.830398977"
        ]
    },
```

- tle: The TLE to propagate.
- exp: The expected values as follows:
  - The first number is the time in minutes after the TLE epoch = `t_min_since_epoch`
  - The next 6 are the position and velocity components in the ECI TEME frame.

The test procedure is to
- load the TLE
- propagate the orbit to `t_min_since_epoch`
- compare the position and velocity with the expected values
