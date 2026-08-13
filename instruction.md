You are given a file at `/app/input.json` containing an array of sensor
readings. Each element of the array is an object with exactly these fields:

- `sensor_id` (string): the identifier of the sensor.
- `value` (number): a single reading recorded by that sensor.

Example `/app/input.json`:

```json
[
  {"sensor_id": "s1", "value": 10.0},
  {"sensor_id": "s1", "value": 20.0},
  {"sensor_id": "s2", "value": 5.5}
]
```

Write a program (in any language available in the container) that reads
`/app/input.json`, groups the readings by `sensor_id`, and writes the result
to `/app/output.json`.

`/app/output.json` must be a single JSON object. Its keys must be the
distinct `sensor_id` values found in the input, and each key must map to an
object with exactly these fields:

- `count` (integer): the number of readings for that sensor.
- `average` (number): the arithmetic mean of the sensor's readings, rounded
  to 2 decimal places.
- `min` (number): the smallest reading for that sensor.
- `max` (number): the largest reading for that sensor.

Requirements:

- The input array may contain any number of sensors (including just one),
  and any number of readings per sensor (at least one reading per sensor
  that appears).
- Every `sensor_id` present in the input must appear exactly once as a key
  in the output.
- `/app/output.json` must be valid JSON that can be parsed with a standard
  JSON parser. Key order and whitespace do not matter.
- Do not hardcode the output. Your program must compute it from whatever
  data is present in `/app/input.json`.
