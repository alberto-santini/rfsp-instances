![Regional airline aircraft](regional-airline.jpg)
<sub><sub>Photo by Sarvesh Lutchmun, CC BY-SA 4.0, via Wikimedia Commons</sub></sub>

# Instances for the RFSP

This repository contains 15 instances for the **Regional Flight Scheduling Problem**.
This problem is introduced in an upcoming paper.
Once the paper will be available, you will find here its bibliographic data and a BibLaTeX entry.

## Structure of the instances

The instances are in `json` format.
They are named `instance-<D>-<A>-<U>.json` where:
* `<D>` is the number of destinations,
* `<A>` is the number of aircraft,
* `<U>` is the minimum utilisation level of each aircraft.

Each instance has the following structure:
* Field `n_destinations` is the number of destinations (the same as `<D>` above).
* Field `n_aircraft` is the number of aircraft (the same as `<A>` above).
* Field `time_horizon_len` is the number of time instants in the time horizon.
* Field `min_utilisaiton` is the per-aircraft minimum utilisation level (same as `<U>` above).
* Field `min_spacing` is the minimum padding time between two flights to the same destination.
* Field `slots` is an array with `time_horizon_len` entries. Each entry is the number of slots available at the hub during the corresponding time interval.
* Field `destinations` is an array with one entry for each of the `n_destinations` destinations. Each destination has fields:
    * `n_flights`, the maximum number of flights to that destination.
    * `flight_time`, the number of time instants for a complete round-trip to that destination. This time includes the turn-around time at both the destination and the hub.
    * `profit`, an array with one entry for each of the `time_horizon_len` time instants. Each entry gives the utility of flying a flight to the given destination at the given time instant.

## License

The instances are released to the public domain through a CC0 1.0 Universal (CC0 1.0) Public Domain Dedication.
See the `LICENSE` file for more information.