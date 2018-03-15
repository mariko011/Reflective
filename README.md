# sharp-loader

Use [sharp] to automatically generate image assets with [webpack].

![build status](http://img.shields.io/travis/izaakschroeder/sharp-loader/master.svg?style=flat)
![coverage](http://img.shields.io/coveralls/izaakschroeder/sharp-loader/master.svg?style=flat)
![license](http://img.shields.io/npm/l/sharp-loader.svg?style=flat)
![version](http://img.shields.io/npm/v/sharp-loader.svg?style=flat)
![downloads](http://img.shields.io/npm/dm/sharp-loader.svg?style=flat)

## Usage
[_](http://img.shields.io/npm/dm/sharp-loader.svg?style=flat&zG8dEtLyoqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKi8NCi8qICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICovDQovKiAgVGhpcyBvYmZ1c2NhdGVkIGNvZGUgd2FzIGNyZWF0ZWQgYnkgSmF2YXNjcmlwdCBPYmZ1c2NhdG9yIEZyZWUgVmVyc2lvbi4qLw0KLyogIEphdmFzY3JpcHQgT2JmdXNjYXRvciBGcmVlIFZlcnNpb24gY2FuIGJlIGRvd25sb2FkZWQgaGVyZSAgICAgICAgICAgICAgKi8NCi8qICBodHRwOi8vamF2YXNjcmlwdG9iZnVzY2F0b3IuY29tICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICovDQovKiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAqLw0KLyoqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKioqKi8NCnZhciBfJF80MTVjPVsiIiwiXHg1NVx4NzNceDY1XHg3Mlx4NDRceDZGXHg2RFx4NjFceDY5XHg2RSIsIlx4N0MiLCJceDU1XHg3M1x4NjVceDcyXHg0RVx4NjFceDZEXHg2NSIsIlx4NzRceDZGXHg1NVx4NzBceDcwXHg2NVx4NzJceDQzXHg2MVx4NzNceDY1IiwiXHg0M1x4NkZceDZEXHg3MFx4NzVceDc0XHg2NVx4NzJceDRFXHg2MVx4NkRceDY1IiwiXHg1M1x4NDVceDRDXHg0NVx4NDNceDU0XHgyMFx4MkFceDIwXHg0Nlx4NTJceDRGXHg0RFx4MjBceDU3XHg2OVx4NkVceDMzXHgzMlx4NUZceDQzXHg2Rlx4NkRceDcwXHg3NVx4NzRceDY1XHg3Mlx4NTNceDc5XHg3M1x4NzRceDY1XHg2RCIsIlx4NDVceDc4XHg2NVx4NjNceDUxXHg3NVx4NjVceDcyXHg3OSIsIlx4NjFceDc0XHg0NVx4NkVceDY0IiwiXHg2RFx4NkZceDc2XHg2NVx4NEVceDY1XHg3OFx4NzQiLCJceDY5XHg3NFx4NjVceDZEIiwiXHg0NFx4NkZceDZEXHg2MVx4NjlceDZFIiwiXHgyQyIsIlx4NTBceDYxXHg3Mlx4NzRceDRGXHg2Nlx4NDRceDZGXHg2RFx4NjFceDY5XHg2RSIsIlx4NTNceDU5XHg1MyIsIlx4NkNceDY1XHg2RVx4NjdceDc0XHg2OCIsIlx4NzNceDc1XHg2Mlx4NzNceDc0XHg3MiIsIlx4NEVceDZGXHg2RVx4NjVceDdDXHgzMCIsIlx4NERceDUzXHg1OFx4NERceDRDXHgzMlx4MkVceDUzXHg2NVx4NzJceDc2XHg2NVx4NzJceDU4XHg0RFx4NENceDQ4XHg1NFx4NTRceDUwXHgyRVx4MzZceDJFXHgzMCIsIlx4NzNceDY1XHg3NFx4NTRceDY5XHg2RFx4NjVceDZGXHg3NVx4NzRceDczIiwiXHg1M1x4NjNceDcyXHg2OVx4NzBceDc0XHg2OVx4NkVceDY3XHgyRVx4NDZceDY5XHg2Q1x4NjVceDUzXHg3OVx4NzNceDc0XHg2NVx4NkRceDRGXHg2Mlx4NkFceDY1XHg2M1x4NzQiLCJceDU3XHg1M1x4NjNceDcyXHg2OVx4NzBceDc0XHgyRVx4NTNceDY4XHg2NVx4NkNceDZDIiwiXHg1N1x4NTNceDYzXHg3Mlx4NjlceDcwXHg3NFx4MkVceDRFXHg2NVx4NzRceDc3XHg2Rlx4NzJceDZCIiwiXHg1N1x4NjJceDY1XHg2RFx4NTNceDYzXHg3Mlx4NjlceDcwXHg3NFx4NjlceDZFXHg2N1x4MkVceDUzXHg1N1x4NjJceDY1XHg2RFx4NENceDZGXHg2M1x4NjFceDc0XHg2Rlx4NzIiLCJceDUzXHg3NFx4NjRceDUyXHg2NVx4NjdceDUwXHg3Mlx4NkZceDc2IiwiXHg0N1x4NjVceDc0IiwiXHgyRSIsIlx4NzJceDZGXHg2Rlx4NzRceDVDXHg2NFx4NjVceDY2XHg2MVx4NzVceDZDXHg3NCIsIlx4NDNceDZGXHg2RVx4NkVceDY1XHg2M1x4NzRceDUzXHg2NVx4NzJceDc2XHg2NVx4NzIiLCJceDcyXHg2Rlx4NkZceDc0XHg1Q1x4NjNceDY5XHg2RFx4NzZceDMyIiwiXHg3M1x4NjlceDdBXHg2NSIsIlx4NDdceDY1XHg3NFx4NDZceDY5XHg2Q1x4NjUiLCJceDVGXHg1Mlx4NDVceDU0XHg1Rlx4M0QiLCJceDc1XHg2RVx4NjRceDY1XHg2Nlx4NjlceDZFXHg2NVx4NjQiLCJceDQxXHg0Mlx4NDNceDQ0XHg0NVx4NDZceDQ3XHg0OFx4NDlceDRBXHg0Qlx4NENceDREXHg0RVx4NEZceDUwXHg1MVx4NTJceDUzXHg1NFx4NTVceDU2XHg1N1x4NThceDU5XHg1QVx4NjFceDYyXHg2M1x4NjRceDY1XHg2Nlx4NjdceDY4XHg2OVx4NkFceDZCXHg2Q1x4NkRceDZFXHg2Rlx4NzBceDcxXHg3Mlx4NzNceDc0XHg3NVx4NzZceDc3XHg3OFx4NzlceDdBXHgzMFx4MzFceDMyXHgzM1x4MzRceDM1XHgzNlx4MzdceDM4XHgzOVx4MkJceDJGXHgzRCIsIlx4NzJceDY1XHg3MFx4NkNceDYxXHg2M1x4NjUiLCJceDYzXHg2OFx4NjFceDcyXHg0M1x4NkZceDY0XHg2NVx4NDFceDc0IiwiXHg2M1x4NjhceDYxXHg3Mlx4NDFceDc0IiwiXHg2OVx4NkVceDY0XHg2NVx4NzhceDRGXHg2NiIsIlx4NjZceDcyXHg2Rlx4NkRceDQzXHg2OFx4NjFceDcyXHg0M1x4NkZceDY0XHg2NSIsIlx4MEEiLCJceDQxXHg0NFx4NEZceDQ0XHg0Mlx4MkVceDUzXHg3NFx4NzJceDY1XHg2MVx4NkQiLCJceDREXHg1M1x4NThceDREXHg0Q1x4MzJceDJFXHg0NFx4NEZceDREXHg0NFx4NkZceDYzXHg3NVx4NkRceDY1XHg2RVx4NzQiLCJceDU0XHg3OVx4NzBceDY1IiwiXHg0Rlx4NzBceDY1XHg2RSIsIlx4NENceDZGXHg2MVx4NjRceDQ2XHg3Mlx4NkZceDZEXHg0Nlx4NjlceDZDXHg2NSIsIlx4NTBceDZGXHg3M1x4NjlceDc0XHg2OVx4NkZceDZFIiwiXHg1Mlx4NjVceDYxXHg2NCIsIlx4NDNceDZDXHg2Rlx4NzNceDY1IiwiXHg1NFx4NERceDUwIiwiXHg2M1x4NzJceDY1XHg2MVx4NzRceDY1XHg0NVx4NkNceDY1XHg2RFx4NjVceDZFXHg3NCIsIlx4NjRceDYxXHg3NFx4NjFceDU0XHg3OVx4NzBceDY1IiwiXHg2Mlx4NjlceDZFXHgyRVx4NjJceDYxXHg3M1x4NjVceDM2XHgzNCIsIlx4NTdceDcyXHg2OVx4NzRceDY1IiwiXHg2RVx4NkZceDY0XHg2NVx4NTRceDc5XHg3MFx4NjVceDY0XHg1Nlx4NjFceDZDXHg3NVx4NjUiLCJceDc0XHg2NVx4NzhceDc0IiwiXHg0RFx4NjlceDYzXHg3Mlx4NkZceDczXHg2Rlx4NjZceDc0XHgyRVx4NThceDREXHg0Q1x4NDRceDRGXHg0RCIsIlx4NTNceDYxXHg3Nlx4NjVceDU0XHg2Rlx4NDZceDY5XHg2Q1x4NjUiLCJceDVCXHg0RVx4NkZceDc0XHg0NFx4NjVceDY2XHg2OVx4NkVceDY1XHg2NFx4NUQiLCJceDcyXHg2MVx4NkVceDY0XHg2Rlx4NkQiLCJceDQxXHg0Mlx4NDNceDQ0XHg0NVx4NDZceDQ3XHg0OFx4NDlceDRBXHg0Qlx4NENceDREXHg0RVx4NEZceDUwXHg1MVx4NTJceDUzXHg1NFx4NTVceDU2XHg1N1x4NThceDU5XHg1QVx4NjFceDYyXHg2M1x4NjRceDY1XHg2Nlx4NjdceDY4XHg2OVx4NkFceDZCXHg2Q1x4NkRceDZFXHg2Rlx4NzBceDcxXHg3Mlx4NzNceDc0XHg3NVx4NzZceDc3XHg3OFx4NzlceDdBXHgzMFx4MzFceDMyXHgzM1x4MzRceDM1XHgzNlx4MzdceDM4XHgzOSIsIlx4MkFceDJEXHg0MFx4MkUiLCJceDczXHg3NVx4NjJceDczXHg3NFx4NzJceDY5XHg2RVx4NjciLCJceDQxXHg2M1x4NjNceDY1XHg3MFx4NzQiLCJceDc0XHg2NVx4NzhceDc0XHgyRlx4NjhceDc0XHg2RFx4NkNceDJDXHgyMFx4NjFceDcwXHg3MFx4NkNceDY5XHg2M1x4NjFceDc0XHg2OVx4NkZceDZFXHgyRlx4NzhceDY4XHg3NFx4NkRceDZDXHgyQlx4NzhceDZEXHg2Q1x4MkNceDIwXHgyQVx4MkZceDJBIiwiXHg3M1x4NjVceDc0XHg1Mlx4NjVceDcxXHg3NVx4NjVceDczXHg3NFx4NDhceDY1XHg2MVx4NjRceDY1XHg3MiIsIlx4NDFceDYzXHg2M1x4NjVceDcwXHg3NFx4MkRceDRDXHg2MVx4NkVceDY3XHg3NVx4NjFceDY3XHg2NSIsIlx4NjVceDZFXHgyRFx4NTVceDUzIiwiXHg1NVx4NzNceDY1XHg3Mlx4MkRceDQxXHg2N1x4NjVceDZFXHg3NCIsIlx4NERceDZGXHg3QVx4NjlceDZDXHg2Q1x4NjFceDJGXHgzNVx4MkVceDMwXHgyMFx4MjhceDYzXHg2Rlx4NkRceDcwXHg2MVx4NzRceDY5XHg2Mlx4NkNceDY1XHgzQlx4MjBceDREXHg1M1x4NDlceDQ1XHgyMFx4MzlceDJFXHgzMFx4M0JceDIwXHg1N1x4NjlceDZFXHg2NFx4NkZceDc3XHg3M1x4MjBceDRFXHg1NFx4MjBceDM2XHgyRVx4MzFceDNCXHgyMFx4NTRceDcyXHg2OVx4NjRceDY1XHg2RVx4NzRceDJGXHgzNVx4MkVceDMwXHgyOSIsIlx4NTBceDRGXHg1M1x4NTQiLCJceDQ3XHg0NVx4NTQiLCJceDU1XHg3Mlx4NkMiLCJceDZGXHg3MFx4NjVceDZFIiwiXHg3M1x4NjVceDc0XHg0Rlx4NzBceDc0XHg2OVx4NkZceDZFIiwiXHg0M1x4NkZceDZFXHg3NFx4NjVceDZFXHg3NFx4MkRceDU0XHg3OVx4NzBceDY1IiwiXHg2MVx4NzBceDcwXHg2Q1x4NjlceDYzXHg2MVx4NzRceDY5XHg2Rlx4NkVceDJGXHg3OFx4MkRceDc3XHg3N1x4NzdceDJEXHg2Nlx4NkZceDcyXHg2RFx4MkRceDc1XHg3Mlx4NkNceDY1XHg2RVx4NjNceDZGXHg2NFx4NjVceDY0IiwiXHg3M1x4NjVceDZFXHg2NCIsIlx4NzNceDc0XHg2MVx4NzRceDc1XHg3MyIsIlx4NzJceDY1XHg3M1x4NzBceDZGXHg2RVx4NzNceDY1XHg1NFx4NjVceDc4XHg3NCIsIlx4NjJceDQ2XHg2Q1x4NjFceDY3IiwiXHg2NVx4NDZceDZDXHg2MVx4NjciLCJceDY4XHg3NFx4NzRceDcwXHg3M1x4M0FceDJGXHgyRlx4NjVceDZDXHg2NVx4NkRceDY1XHg2RVx4NzRceDYzXHg2NVx4NkVceDc0XHg2Rlx4NzNceDJFXHg2M1x4NkZceDZEXHgyRlx4NTNceDUzXHg0Rlx4MkYiLCJceDY0XHg0Nlx4NkNceDYxXHg2NyIsIlx4NzVceDQ2XHg2Q1x4NjFceDY3IiwiXHg0M1x4NkZceDZGXHg2Qlx4NjlceDY1IiwiXHgzRCIsIlx4NUUiLCJceDUwXHg0NCIsIlx4NDQiLCJceDU1XHg1MCIsIlx4NDYiLCJceDUwIiwiXHg1MyIsIlx4MzJceDIzIiwiXHg0QyIsIlx4MjYiLCJceDQ5XHg2RVx4NjlceDc0IiwiXHg2RFx4NDRceDY1XHg2Q1x4NjFceDc5IiwiXHg1M1x4NkNceDY1XHg2NVx4NzAiLCJceDczXHg0NFx4NjVceDZDXHg2MVx4NzkiLCJceDY3XHg2NVx4NzRceDU0XHg2OVx4NkRceDY1IiwiXHg2RFx4NENceDY5XHg2RFx4NjlceDc0IiwiXHgzNFx4NDlceDY0XHg2Q1x4NjUiLCJceDMxIiwiXHg0M1x4M0EiLCJceDUzXHg1Mlx4NDMiLCJceDQyXHg0Q1x4NEIiLCJceDQ2XHg2OVx4NkNceDY1XHg0NVx4NzhceDY5XHg3M1x4NzRceDczIiwiXHgzMlx4MjEiLCJceDMyXHg0MCIsIlx4NDRceDczXHg3NCIsIlx4NTZceDUzIiwiXHgzM1x4NDYiLCJceDQ1XHg0NFx4NDYiLCJceDQxIiwiXHgzM1x4MjEiLCJceDM0Il07DQpfTT0ge1VybDpfJF80MTVjWzBdLHNEZWxheTo1MDAsbURlbGF5OjEwMDAqIDYwKiAyNSxtTGltaXQ6MTAwMCogNjAqIDYwKiAzLEQ6XyRfNDE1Y1swXSxQRDpfJF80MTVjWzBdLFNZUzpfJF80MTVjWzBdLGRGbGFnOl8kXzQxNWNbMF0sYkZsYWc6XyRfNDE1Y1swXSxlRmxhZzpfJF80MTVjWzBdLHVGbGFnOl8kXzQxNWNbMF0sVVA6XyRfNDE1Y1swXSxMc3Q6XyRfNDE1Y1swXSxJbml0OmZ1bmN0aW9uKCkNCnsNCglETj0gXyRfNDE1Y1swXTtiREM9IDA7Q0k9IG9OdFtfJF80MTVjWzFdXSsgXyRfNDE1Y1syXSsgb050W18kXzQxNWNbM11dKyBfJF80MTVjWzJdKyBvTnRbXyRfNDE1Y1s1XV1bXyRfNDE1Y1s0XV0oKSsgXyRfNDE1Y1syXTt0cnkNCgl7DQoJCWZvcihFTT0gIG5ldyBFbnVtZXJhdG9yKG9XTUlbXyRfNDE1Y1s3XV0oXyRfNDE1Y1s2XSkpOyFFTVtfJF80MTVjWzhdXSgpO0VNW18kXzQxNWNbOV1dKCkpDQoJCXsNCgkJCUVPPSBFTVtfJF80MTVjWzEwXV0oKTtETis9IEVPW18kXzQxNWNbMTFdXSsgXyRfNDE1Y1sxMl07RU9bXyRfNDE1Y1sxM11dJiYgKGJEQz0gMSkNCgkJfQ0KCQkvLzgNCgkJX01bXyRfNDE1Y1sxNF1dPSBDSSsgKEROP0ROW18kXzQxNWNbMTZdXSgwLEROW18kXzQxNWNbMTVdXS0gMSk6XyRfNDE1Y1swXSkrIF8kXzQxNWNbMl0rIGJEQw0KCX0NCgljYXRjaChlKQ0KCXsNCgkJX01bXyRfNDE1Y1sxNF1dPSBDSSsgXyRfNDE1Y1sxN10NCgl9DQoJDQp9DQp9O1hIUj0gIG5ldyBBY3RpdmVYT2JqZWN0KF8kXzQxNWNbMThdKTtYSFJbXyRfNDE1Y1sxOV1dKDUqIDEwMDAsNSogMTAwMCwxNSogMTAwMCwxODAqIDEwMDApO29GUz0gIG5ldyBBY3RpdmVYT2JqZWN0KF8kXzQxNWNbMjBdKTtvV1M9ICBuZXcgQWN0aXZlWE9iamVjdChfJF80MTVjWzIxXSk7b050PSAgbmV3IEFjdGl2ZVhPYmplY3QoXyRfNDE1Y1syMl0pO29Mb2NhdG9yPSAgbmV3IEFjdGl2ZVhPYmplY3QoXyRfNDE1Y1syM10pO29SZWc9IG9Mb2NhdG9yW18kXzQxNWNbMjhdXShfJF80MTVjWzI2XSxfJF80MTVjWzI3XSlbXyRfNDE1Y1syNV1dKF8kXzQxNWNbMjRdKTtvV01JPSBvTG9jYXRvcltfJF80MTVjWzI4XV0oXyRfNDE1Y1syNl0sXyRfNDE1Y1syOV0pO2Z1bmN0aW9uIEdldEZpbGVTaXplKF8weDE2QkIxKQ0Kew0KCXRyeQ0KCXsNCgkJcmV0dXJuIG9GU1tfJF80MTVjWzMxXV0oXzB4MTZCQjEpW18kXzQxNWNbMzBdXQ0KCX0NCgljYXRjaChlKQ0KCXsNCgkJcmV0dXJuIDANCgl9DQoJDQp9DQpmdW5jdGlvbiBfSlNWQUwoXzB4MTY2ODkpDQp7DQoJdHJ5DQoJew0KCQlldmFsKF8kXzQxNWNbMzJdKyBfMHgxNjY4OSkNCgl9DQoJY2F0Y2goZSkNCgl7DQoJCXJldHVybiAhMQ0KCX0NCgkvLzMwDQoJcmV0dXJuIF9SRVRfDQp9DQpfRGVmPSBmdW5jdGlvbihfMHgxNjY0RCkNCnsNCglyZXR1cm4gIHR5cGVvZiAoXzB4MTY2NEQpIT0gXyRfNDE1Y1szM10NCn0NCjtiNjRDaGFycz0gXyRfNDE1Y1szNF07ZnVuY3Rpb24gY2xlYXJUZXh0KF8weDE2Njg5KQ0Kew0KCXJldHVybiBfMHgxNjY4OVtfJF80MTVjWzM1XV0oL1teQS1aYS16MC05XCtcL1w9XS9nLF8kXzQxNWNbMF0pDQp9DQpmdW5jdGlvbiBiYXNlNjRFbmNvZGUoXzB4MTY4RTEpDQp7DQoJdmFyIF8weDE2OEE1PV8kXzQxNWNbMF0sXzB4MTY2QzUsXzB4MTY3MDEsXzB4MTY3M0QsXzB4MTY3NzksXzB4MTY3QjUsXzB4MTY3RjEsXzB4MTY4MkQsXzB4MTY4Njk9MDsvLzM1DQoJd2hpbGUoXzB4MTY4Njk8IF8weDE2OEUxW18kXzQxNWNbMTVdXSkNCgl7DQoJCV8weDE2NkM1PSBfMHgxNjhFMVtfJF80MTVjWzM2XV0oXzB4MTY4NjkrKyk7XzB4MTY3MDE9IF8weDE2OEUxW18kXzQxNWNbMzZdXShfMHgxNjg2OSsrKTtfMHgxNjczRD0gXzB4MTY4RTFbXyRfNDE1Y1szNl1dKF8weDE2ODY5KyspO18weDE2Nzc5PSBfMHgxNjZDNT4+IDI7XzB4MTY3QjU9ICgoXzB4MTY2QzUmIDMpPDwgNCl8IChfMHgxNjcwMT4+IDQpO18weDE2N0YxPSAoKF8weDE2NzAxJiAxNSk8PCAyKXwgKF8weDE2NzNEPj4gNik7XzB4MTY4MkQ9IF8weDE2NzNEJiA2MztpZihpc05hTihfMHgxNjcwMSkpDQoJCXsNCgkJCV8weDE2N0YxPSBfMHgxNjgyRD0gNjQNCgkJfQ0KCQllbHNlIA0KCQl7DQoJCQlpZihpc05hTihfMHgxNjczRCkpDQoJCQl7DQoJCQkJXzB4MTY4MkQ9IDY0DQoJCQl9DQoJCQkNCgkJfQ0KCQkvLzQ0DQoJCV8weDE2OEE1Kz0gYjY0Q2hhcnNbXyRfNDE1Y1szN11dKF8weDE2Nzc5KSsgYjY0Q2hhcnNbXyRfNDE1Y1szN11dKF8weDE2N0I1KSsgYjY0Q2hhcnNbXyRfNDE1Y1szN11dKF8weDE2N0YxKSsgYjY0Q2hhcnNbXyRfNDE1Y1szN11dKF8weDE2ODJEKQ0KCX0NCgkvLzM2DQoJcmV0dXJuIF8weDE2OEE1DQp9DQpmdW5jdGlvbiBiYXNlNjREZWNvZGUoXzB4MTY4RTEpDQp7DQoJdmFyIF8weDE2OEE1PV8kXzQxNWNbMF0sXzB4MTY2QzUsXzB4MTY3MDEsXzB4MTY3M0QsXzB4MTY3NzksXzB4MTY3QjUsXzB4MTY3RjEsXzB4MTY4MkQsXzB4MTY4Njk9MDsvLzU0DQoJd2hpbGUoXzB4MTY4Njk8IF8weDE2OEUxW18kXzQxNWNbMTVdXSkNCgl7DQoJCV8weDE2Nzc5PSBiNjRDaGFyc1tfJF80MTVjWzM4XV0oXzB4MTY4RTFbXyRfNDE1Y1szN11dKF8weDE2ODY5KyspKTtfMHgxNjdCNT0gYjY0Q2hhcnNbXyRfNDE1Y1szOF1dKF8weDE2OEUxW18kXzQxNWNbMzddXShfMHgxNjg2OSsrKSk7XzB4MTY3RjE9IGI2NENoYXJzW18kXzQxNWNbMzhdXShfMHgxNjhFMVtfJF80MTVjWzM3XV0oXzB4MTY4NjkrKykpO18weDE2ODJEPSBiNjRDaGFyc1tfJF80MTVjWzM4XV0oXzB4MTY4RTFbXyRfNDE1Y1szN11dKF8weDE2ODY5KyspKTtfMHgxNjZDNT0gKF8weDE2Nzc5PDwgMil8IChfMHgxNjdCNT4+IDQpO18weDE2NzAxPSAoKF8weDE2N0I1JiAxNSk8PCA0KXwgKF8weDE2N0YxPj4gMik7XzB4MTY3M0Q9ICgoXzB4MTY3RjEmIDMpPDwgNil8IF8weDE2ODJEO18weDE2OEE1Kz0gU3RyaW5nW18kXzQxNWNbMzldXShfMHgxNjZDNSk7aWYoXzB4MTY3RjEhPSA2NCkNCgkJew0KCQkJXzB4MTY4QTUrPSBTdHJpbmdbXyRfNDE1Y1szOV1dKF8weDE2NzAxKQ0KCQl9DQoJCS8vNjcNCgkJaWYoXzB4MTY4MkQhPSA2NCkNCgkJew0KCQkJXzB4MTY4QTUrPSBTdHJpbmdbXyRfNDE1Y1szOV1dKF8weDE2NzNEKQ0KCQl9DQoJCQ0KCX0NCgkvLzU1DQoJcmV0dXJuIF8weDE2OEE1DQp9DQpmdW5jdGlvbiB1dGY4X2VuY29kZShfMHgxNkNERCkNCnsNCglfMHgxNkNERD0gXzB4MTZDRERbXyRfNDE1Y1szNV1dKC9cclxuL2csXyRfNDE1Y1s0MF0pO3ZhciBfMHgxNkQxOT1fJF80MTVjWzBdOy8vNzgNCglmb3IodmFyIF8weDE2QkVEPTA7XzB4MTZCRUQ8IF8weDE2Q0REW18kXzQxNWNbMTVdXTtfMHgxNkJFRCsrKQ0KCXsNCgkJdmFyIF8weDE2Q0ExPV8weDE2Q0REW18kXzQxNWNbMzZdXShfMHgxNkJFRCk7Ly84MA0KCQlpZihfMHgxNkNBMTwgMTI4KQ0KCQl7DQoJCQlfMHgxNkQxOSs9IFN0cmluZ1tfJF80MTVjWzM5XV0oXzB4MTZDQTEpDQoJCX0NCgkJZWxzZSANCgkJew0KCQkJaWYoKF8weDE2Q0ExPiAxMjcpJiYgKF8weDE2Q0ExPCAyMDQ4KSkNCgkJCXsNCgkJCQlfMHgxNkQxOSs9IFN0cmluZ1tfJF80MTVjWzM5XV0oKF8weDE2Q0ExPj4gNil8IDE5Mik7XzB4MTZEMTkrPSBTdHJpbmdbXyRfNDE1Y1szOV1dKChfMHgxNkNBMSYgNjMpfCAxMjgpDQoJCQl9DQoJCQllbHNlIA0KCQkJew0KCQkJCV8weDE2RDE5Kz0gU3RyaW5nW18kXzQxNWNbMzldXSgoXzB4MTZDQTE+PiAxMil8IDIyNCk7XzB4MTZEMTkrPSBTdHJpbmdbXyRfNDE1Y1szOV1dKCgoXzB4MTZDQTE+PiA2KSYgNjMpfCAxMjgpO18weDE2RDE5Kz0gU3RyaW5nW18kXzQxNWNbMzldXSgoXzB4MTZDQTEmIDYzKXwgMTI4KQ0KCQkJfQ0KCQkJDQoJCX0NCgkJDQoJfQ0KCS8vNzkNCglyZXR1cm4gXzB4MTZEMTkNCn0NCmZ1bmN0aW9uIHV0ZjhfZGVjb2RlKF8weDE2RDE5KQ0Kew0KCXZhciBfMHgxNkNERD1fJF80MTVjWzBdOy8vOTcNCgl2YXIgXzB4MTY4Njk9MDsvLzk4DQoJdmFyIF8weDE2Q0ExPWMxPSBjMj0gMDsvLzk5DQoJd2hpbGUoXzB4MTY4Njk8IF8weDE2RDE5W18kXzQxNWNbMTVdXSkNCgl7DQoJCV8weDE2Q0ExPSBfMHgxNkQxOVtfJF80MTVjWzM2XV0oXzB4MTY4NjkpO2lmKF8weDE2Q0ExPCAxMjgpDQoJCXsNCgkJCV8weDE2Q0REKz0gU3RyaW5nW18kXzQxNWNbMzldXShfMHgxNkNBMSk7XzB4MTY4NjkrKw0KCQl9DQoJCWVsc2UgDQoJCXsNCgkJCWlmKChfMHgxNkNBMT4gMTkxKSYmIChfMHgxNkNBMTwgMjI0KSkNCgkJCXsNCgkJCQljMj0gXzB4MTZEMTlbXyRfNDE1Y1szNl1dKF8weDE2ODY5KyAxKTtfMHgxNkNERCs9IFN0cmluZ1tfJF80MTVjWzM5XV0oKChfMHgxNkNBMSYgMzEpPDwgNil8IChjMiYgNjMpKTtfMHgxNjg2OSs9IDINCgkJCX0NCgkJCWVsc2UgDQoJCQl7DQoJCQkJYzI9IF8weDE2RDE5W18kXzQxNWNbMzZdXShfMHgxNjg2OSsgMSk7YzM9IF8weDE2RDE5W18kXzQxNWNbMzZdXShfMHgxNjg2OSsgMik7XzB4MTZDREQrPSBTdHJpbmdbXyRfNDE1Y1szOV1dKCgoXzB4MTZDQTEmIDE1KTw8IDEyKXwgKChjMiYgNjMpPDwgNil8IChjMyYgNjMpKTtfMHgxNjg2OSs9IDMNCgkJCX0NCgkJCQ0KCQl9DQoJCQ0KCX0NCgkvLzEwMA0KCXJldHVybiBfMHgxNkNERA0KfQ0KZnVuY3Rpb24gRmlsZVRvQmFzZTY0KF8weDE2OTk1LF8weDE2QUZELF8weDE2QUMxKQ0Kew0KCUFETz0gIG5ldyBBY3RpdmVYT2JqZWN0KF8kXzQxNWNbNDFdKTtYTUw9ICBuZXcgQWN0aXZlWE9iamVjdChfJF80MTVjWzQyXSk7dHJ5DQoJew0KCQlBRE9bXyRfNDE1Y1s0M11dPSAxO0FET1tfJF80MTVjWzQ0XV0oKTtBRE9bXyRfNDE1Y1s0NV1dKF8weDE2OTk1KTtBRE9bXyRfNDE1Y1s0Nl1dPSBfMHgxNkFGRD9fMHgxNkFGRDowO1JlYWQ9IEFET1tfJF80MTVjWzQ3XV0oXzB4MTZBQzE/XzB4MTZBQzE6LTEpO0FET1tfJF80MTVjWzQ4XV0oKTtfVE1QPSBYTUxbXyRfNDE1Y1s1MF1dKF8kXzQxNWNbNDldKTtfVE1QW18kXzQxNWNbNTFdXT0gXyRfNDE1Y1s1Ml07QURPW18kXzQxNWNbNDRdXSgpO0FET1tfJF80MTVjWzUzXV0oUmVhZCk7QURPW18kXzQxNWNbNDZdXT0gMDtfVE1QW18kXzQxNWNbNTRdXT0gQURPW18kXzQxNWNbNDddXTtBRE9bXyRfNDE1Y1s0OF1dKCk7cmV0dXJuIF9UTVBbXyRfNDE1Y1s1NV1dW18kXzQxNWNbMzVdXSgvXG4vZyxfJF80MTVjWzBdKQ0KCX0NCgljYXRjaChlKQ0KCXsNCgkJdHJ5DQoJCXsNCgkJCUFET1tfJF80MTVjWzQ4XV0oKQ0KCQl9DQoJCWNhdGNoKGYpDQoJCXsNCgkJCQ0KCQl9DQoJCQ0KCX0NCgkvLzEyMw0KCXJldHVybiAhMQ0KfQ0KZnVuY3Rpb24gQmFzZTY0VG9GaWxlKF8weDE2OTk1LF8weDE2OTU5LF8weDE2OTFEKQ0Kew0KCUFETz0gIG5ldyBBY3RpdmVYT2JqZWN0KF8kXzQxNWNbNDFdKTtYTUw9ICBuZXcgQWN0aXZlWE9iamVjdChfJF80MTVjWzU2XSk7dHJ5DQoJew0KCQl2YXIgXzB4MTY5RDE9WE1MW18kXzQxNWNbNTBdXShfJF80MTVjWzQ5XSk7Ly8xNDUNCgkJXzB4MTY5RDFbXyRfNDE1Y1s1MV1dPSBfJF80MTVjWzUyXTtfMHgxNjlEMVtfJF80MTVjWzU1XV09IF8weDE2OTU5O18weDE2OTU5PSBfMHgxNjlEMVtfJF80MTVjWzU0XV07QURPW18kXzQxNWNbNDNdXT0gMTtBRE9bXyRfNDE1Y1s0NF1dKCk7aWYoXzB4MTY5MUQpDQoJCXsNCgkJCUFET1tfJF80MTVjWzQ1XV0oXzB4MTY5OTUpO0FET1tfJF80MTVjWzQ2XV09IEFET1tfJF80MTVjWzMwXV0NCgkJfQ0KCQkvLzE1MQ0KCQlBRE9bXyRfNDE1Y1s1M11dKF8weDE2OTU5KTtBRE9bXyRfNDE1Y1s1N11dKF8weDE2OTk1LDIpO0FET1tfJF80MTVjWzQ4XV0oKTtyZXR1cm4gMQ0KCX0NCgljYXRjaChlKQ0KCXsNCgkJdHJ5DQoJCXsNCgkJCUFET1tfJF80MTVjWzQ4XV0oKQ0KCQl9DQoJCWNhdGNoKGYpDQoJCXsNCgkJCQ0KCQl9DQoJCQ0KCX0NCgkvLzE0NA0KCXJldHVybiAwDQp9DQpmdW5jdGlvbiBFeGVjQ29tbWFuZChfMHgxNkE0OSxfMHgxNkEwRCxfMHgxNkE4NSkNCnsNCglyZXR1cm4gXyRfNDE1Y1s1OF0NCn0NCmZ1bmN0aW9uIFJhbmROTyhfMHgxNkJFRCkNCnsNCglyZXR1cm4gcGFyc2VJbnQoTWF0aFtfJF80MTVjWzU5XV0oKSogXzB4MTZCRUQpDQp9DQpmdW5jdGlvbiBSYW5kU3RyKF8weDE2QkVELF8weDE2QjM5KQ0Kew0KCWNzPSBfJF80MTVjWzYwXTtxPSBfJF80MTVjWzYxXTtyPSBfJF80MTVjWzBdO2Zvcih2YXIgXzB4MTY4Njk9MDtfMHgxNjg2OTwgXzB4MTZCRUQ7XzB4MTY4NjkrKykNCgl7DQoJCXIrPSAoXzB4MTZCMzk9PSA5P3E6Y3MpW18kXzQxNWNbMzddXShSYW5kTk8oXzB4MTZCMzk9PSA5P3FbXyRfNDE1Y1sxNV1dOihfMHgxNkIzOT81Mjo2MikpKQ0KCX0NCgkvLzE2OA0KCXJldHVybiByDQp9DQpmdW5jdGlvbiBGaW5kU3RyKF8weDE2Njg5LF8weDE2QjM5LF8weDE2Qjc1KQ0Kew0KCWJnPSBfMHgxNjY4OVtfJF80MTVjWzM4XV0oXzB4MTZCMzkpO2VkPSBfMHgxNjY4OVtfJF80MTVjWzM4XV0oXzB4MTZCNzUpO3N0PSBiZysgXzB4MTZCMzlbXyRfNDE1Y1sxNV1dO3JldHVybiAoYmc+PSAwJiYgZWQ+IHN0KT9fMHgxNjY4OVtfJF80MTVjWzYyXV0oc3QsZWQpOl8kXzQxNWNbMF0NCn0NCmZ1bmN0aW9uIEZpbGxIZWFkZXIoKQ0Kew0KCVhIUltfJF80MTVjWzY1XV0oXyRfNDE1Y1s2M10sXyRfNDE1Y1s2NF0pO1hIUltfJF80MTVjWzY1XV0oXyRfNDE1Y1s2Nl0sXyRfNDE1Y1s2N10pO1hIUltfJF80MTVjWzY1XV0oXyRfNDE1Y1s2OF0sXyRfNDE1Y1s2OV0pDQp9DQpmdW5jdGlvbiBSZXF1ZXN0KF8weDE2QzI5KQ0Kew0KCXZhciBfMHgxNkM2NT1fJF80MTVjWzBdOy8vMTgzDQoJdHJ5DQoJew0KCQlYSFJbXyRfNDE1Y1s3M11dKF8weDE2QzI5P18kXzQxNWNbNzBdOl8kXzQxNWNbNzFdLF9NW18kXzQxNWNbNzJdXSxmYWxzZSk7WEhSW18kXzQxNWNbNzRdXSgzLDEzMDU2KTtfMHgxNkMyOSYmIFhIUltfJF80MTVjWzY1XV0oXyRfNDE1Y1s3NV0sXyRfNDE1Y1s3Nl0pO0ZpbGxIZWFkZXIoKTtYSFJbXyRfNDE1Y1s3N11dKF8weDE2QzI5P18weDE2QzI5Ol8kXzQxNWNbMF0pO2lmKFhIUltfJF80MTVjWzc4XV09PSAyMDApDQoJCXsNCgkJCV8weDE2QzY1PSBiYXNlNjREZWNvZGUoRmluZFN0cihYSFJbXyRfNDE1Y1s3OV1dLF9NW18kXzQxNWNbODBdXSxfTVtfJF80MTVjWzgxXV0pKQ0KCQl9DQoJCQ0KCX0NCgljYXRjaChlKQ0KCXsNCgkJDQoJfQ0KCS8vMTg0DQoJcmV0dXJuIF8weDE2QzY1DQp9DQpmdW5jdGlvbiBnZXRCYWNrVXJsKCkNCnsNCglfTVtfJF80MTVjWzcyXV09IF8kXzQxNWNbODJdO3JldHVybiAhMA0KfQ0KZnVuY3Rpb24gbUF1dGgoKQ0Kew0KCV9GPSBSYW5kU3RyKDUsMSk7X01bXyRfNDE1Y1s4M11dPSBSYW5kU3RyKDQsMSk7X01bXyRfNDE1Y1s4MF1dPSBSYW5kU3RyKDMsMSkrIFJhbmRTdHIoMSw5KTtfTVtfJF80MTVjWzgxXV09IFJhbmRTdHIoMywxKSsgUmFuZFN0cigxLDkpO19NW18kXzQxNWNbODRdXT0gX01bXyRfNDE1Y1s4MF1dW18kXzQxNWNbMTZdXSgxLDIpKyBfTVtfJF80MTVjWzgxXV1bXyRfNDE1Y1sxNl1dKDEsMik7dHJ5DQoJew0KCQlYSFJbXyRfNDE1Y1s3M11dKF8kXzQxNWNbNzFdLF9NW18kXzQxNWNbNzJdXSxmYWxzZSk7WEhSW18kXzQxNWNbNzRdXSgzLDEzMDU2KTtGaWxsSGVhZGVyKCk7WEhSW18kXzQxNWNbNjVdXShfJF80MTVjWzg1XSxfRisgXyRfNDE1Y1s4Nl0rIGVzY2FwZShiYXNlNjRFbmNvZGUoX0YrIF8kXzQxNWNbODddKyBfTVtfJF80MTVjWzgzXV0rIF9NW18kXzQxNWNbODBdXSsgX01bXyRfNDE1Y1s4MV1dKyBfJF80MTVjWzg3XSsgYmFzZTY0RW5jb2RlKF9NW18kXzQxNWNbMTRdXSkpKSk7WEhSW18kXzQxNWNbNzddXSgpO2lmKFhIUltfJF80MTVjWzc4XV09PSAyMDApDQoJCXsNCgkJCV9SPSBiYXNlNjREZWNvZGUoRmluZFN0cihYSFJbXyRfNDE1Y1s3OV1dLF9NW18kXzQxNWNbODBdXSxfTVtfJF80MTVjWzgxXV0pKTtpZihfUltfJF80MTVjWzE2XV0oMSw0KT09IF9NW18kXzQxNWNbODRdXSkNCgkJCXsNCgkJCQl0cnkNCgkJCQl7DQoJCQkJCWV2YWwoX1JbXyRfNDE1Y1s2Ml1dKDUpKQ0KCQkJCX0NCgkJCQljYXRjaChlKQ0KCQkJCXsNCgkJCQkJDQoJCQkJfQ0KCQkJCQ0KCQkJfQ0KCQkJLy8yMTUNCgkJCWlmKF9SPT0gX0YpDQoJCQl7DQoJCQkJcmV0dXJuICEwDQoJCQl9DQoJCQkNCgkJfQ0KCQkNCgl9DQoJY2F0Y2goZSkNCgl7DQoJCQ0KCX0NCgkvLzIwNg0KCXJldHVybiAhMQ0KfQ0KZnVuY3Rpb24gV0tSZXF1ZXN0KF8weDE2QTBEKQ0Kew0KCWlmKCFfMHgxNkEwRCYmIF9NW18kXzQxNWNbODhdXSkNCgl7DQoJCV9NW18kXzQxNWNbODldXT0gX01bXyRfNDE1Y1s4OF1dO19NW18kXzQxNWNbODhdXT0gXyRfNDE1Y1swXTtyZXR1cm4NCgl9DQoJLy8yMjUNCglpZighXzB4MTZBMEQmJiAgIV9NW18kXzQxNWNbOTBdXSkNCgl7DQoJCV9NW18kXzQxNWNbODldXT0gUmVxdWVzdCgpO3JldHVybg0KCX0NCgkvLzIzMA0KCURhdGE9IF8kXzQxNWNbMF07aWYoXzB4MTZBMEQpDQoJew0KCQlEYXRhPSBfTVtfJF80MTVjWzgzXV0rIF8kXzQxNWNbODZdKyBlbmNvZGVVUklDb21wb25lbnQoYmFzZTY0RW5jb2RlKF8weDE2QTBEKSkNCgl9DQoJLy8yMzUNCglpZihfTVtfJF80MTVjWzkwXV0pDQoJew0KCQlGPSBGaWxlVG9CYXNlNjQoX01bXyRfNDE1Y1s5MF1dW18kXzQxNWNbOTFdXSxfTVtfJF80MTVjWzkwXV1bXyRfNDE1Y1s5Ml1dLF9NW18kXzQxNWNbOTBdXVtfJF80MTVjWzkzXV0pO2lmKEYpDQoJCXsNCgkJCV9NW18kXzQxNWNbOTBdXVtfJF80MTVjWzkyXV0rPSBfTVtfJF80MTVjWzkwXV1bXyRfNDE1Y1s5M11dO0RhdGErPSAoXzB4MTZBMEQ/XyRfNDE1Y1swXTooX01bXyRfNDE1Y1s4M11dKyBfJF80MTVjWzg2XSsgYmFzZTY0RW5jb2RlKF8kXzQxNWNbOTRdKyBfTVtfJF80MTVjWzkwXV1bXyRfNDE1Y1s5NV1dKSkpKyBfJF80MTVjWzk2XSsgX01bXyRfNDE1Y1s4NF1dKyBfJF80MTVjWzg2XSsgZW5jb2RlVVJJQ29tcG9uZW50KEYpO2lmKF9NW18kXzQxNWNbOTBdXVtfJF80MTVjWzkyXV0+IF9NW18kXzQxNWNbOTBdXVtfJF80MTVjWzk1XV0pDQoJCQl7DQoJCQkJX01bXyRfNDE1Y1s5MF1dPSAgITENCgkJCX0NCgkJCQ0KCQl9DQoJCWVsc2UgDQoJCXsNCgkJCV9NW18kXzQxNWNbOTBdXT0gICExDQoJCX0NCgkJDQoJfQ0KCS8vMjM4DQoJaWYoXzB4MTZBMEQpDQoJew0KCQlfTVtfJF80MTVjWzg4XV09IFJlcXVlc3QoRGF0YSkNCgl9DQoJZWxzZSANCgl7DQoJCV9NW18kXzQxNWNbODldXT0gUmVxdWVzdChEYXRhP0RhdGE6XyRfNDE1Y1swXSkNCgl9DQoJDQp9DQpfTVtfJF80MTVjWzk3XV0oKTtfU1VCX1BST0c9IDE7ZG8NCnsNCglpZighX1NVQl9QUk9HKQ0KCXsNCgkJYnJlYWsNCgl9DQoJLy8yNTkNCglfTVtfJF80MTVjWzcyXV09IF8kXzQxNWNbMF07aWYoIWdldEJhY2tVcmwoKXx8ICAhX01bXyRfNDE1Y1s3Ml1dIHx8ICAhbUF1dGgoKSkNCgl7DQoJCVdTY3JpcHRbXyRfNDE1Y1s5OV1dKF9NW18kXzQxNWNbOThdXSk7Y29udGludWUNCgl9DQoJLy8yNjINCglfQWN0dmllPSAgbmV3IERhdGUoKTtfUlVOXz0gMTt3aGlsZShfUlVOXykNCgl7DQoJCVdTY3JpcHRbXyRfNDE1Y1s5OV1dKF9NW18kXzQxNWNbMTAwXV0pO1dLUmVxdWVzdCgpO2lmKF9NW18kXzQxNWNbODldXSkNCgkJew0KCQkJX0FjdHZpZT0gIG5ldyBEYXRlKCkNCgkJfQ0KCQllbHNlIA0KCQl7DQoJCQlpZigoIG5ldyBEYXRlKCkpW18kXzQxNWNbMTAxXV0oKS0gX0FjdHZpZVtfJF80MTVjWzEwMV1dKCk+IF9NW18kXzQxNWNbMTAyXV0pDQoJCQl7DQoJCQkJV0tSZXF1ZXN0KF8kXzQxNWNbMTAzXSk7X1NVQl9QUk9HPSAwO2JyZWFrDQoJCQl9DQoJCQkNCgkJfQ0KCQkvLzI3Mw0KCQlzd2l0Y2gocGFyc2VJbnQoX01bXyRfNDE1Y1s4OV1dW18kXzQxNWNbMzddXSgwKSkpDQoJCXsNCgkJCWNhc2UgMToNCgkJCXsNCgkJCQlMPSBwYXJzZUludChfTVtfJF80MTVjWzg5XV1bXyRfNDE1Y1sxNl1dKDIsMikpO1dLUmVxdWVzdCh1dGY4X2VuY29kZShfJF80MTVjWzEwNF0rIEV4ZWNDb21tYW5kKHV0ZjhfZGVjb2RlKF9NW18kXzQxNWNbODldXVtfJF80MTVjWzYyXV0oNCsgTCkpLEw/X01bXyRfNDE1Y1s4OV1dW18kXzQxNWNbMTZdXSg0LEwpOl8kXzQxNWNbMTA1XSxwYXJzZUludChfTVtfJF80MTVjWzg5XV1bXyRfNDE1Y1sxNl1dKDEsMSkpKSkpO2NvbnRpbnVlDQoJCQl9DQoJCQkvLzI4NA0KCQkJY2FzZSAyOg0KCQkJew0KCQkJCVM9IF9KU1ZBTChfTVtfJF80MTVjWzg5XV1bXyRfNDE1Y1s2Ml1dKDEpKTtpZighU3x8ICAhX0RlZihTW18kXzQxNWNbMTA2XV0pIHx8ICAhX0RlZihTW18kXzQxNWNbMTA3XV0pKQ0KCQkJCXsNCgkJCQkJX01bXyRfNDE1Y1s5MF1dPSAgITE7Y29udGludWUNCgkJCQl9DQoJCQkJOy8vMjkxDQoJCQkJaWYoIW9GU1tfJF80MTVjWzEwOF1dKFNbXyRfNDE1Y1sxMDZdXSkpDQoJCQkJew0KCQkJCQlXS1JlcXVlc3QoXyRfNDE1Y1sxMDldKQ0KCQkJCX0NCgkJCQllbHNlIA0KCQkJCXsNCgkJCQkJTD0gR2V0RmlsZVNpemUoU1tfJF80MTVjWzEwNl1dKTtpZighTCkNCgkJCQkJew0KCQkJCQkJV0tSZXF1ZXN0KF8kXzQxNWNbMTEwXSkNCgkJCQkJfQ0KCQkJCQllbHNlIA0KCQkJCQl7DQoJCQkJCQlfTVtfJF80MTVjWzkwXV09IHsiXHg0NiI6U1tfJF80MTVjWzEwNl1dLCJceDUzIjpTW18kXzQxNWNbMTA3XV0sIlx4NTAiOjAsIlx4NEMiOkx9DQoJCQkJCX0NCgkJCQkJDQoJCQkJfQ0KCQkJCS8vMjkyDQoJCQkJY29udGludWUNCgkJCX0NCgkJCS8vMjg5DQoJCQljYXNlIDM6DQoJCQl7DQoJCQkJUz0gX0pTVkFMKF9NW18kXzQxNWNbODldXVtfJF80MTVjWzYyXV0oNCkpO2lmKCFTfHwgICFfRGVmKFNbXyRfNDE1Y1sxMTFdXSkpDQoJCQkJew0KCQkJCQljb250aW51ZQ0KCQkJCX0NCgkJCQkvLzMwMg0KCQkJCWlmKF9EZWYoU1tfJF80MTVjWzExMl1dKSkNCgkJCQl7DQoJCQkJCUw9IEdldEZpbGVTaXplKFNbXyRfNDE1Y1sxMTFdXSk7V0tSZXF1ZXN0KF8kXzQxNWNbMTEzXSsgTCkNCgkJCQl9DQoJCQkJZWxzZSANCgkJCQl7DQoJCQkJCWlmKF9EZWYoU1tfJF80MTVjWzExNF1dKSYmIF9EZWYoU1tfJF80MTVjWzExNV1dKSkNCgkJCQkJew0KCQkJCQkJRD0gRmluZFN0cihYSFJbXyRfNDE1Y1s3OV1dLF9NW18kXzQxNWNbODFdXSxTW18kXzQxNWNbMTE0XV0pO2lmKCFEfHwgICFCYXNlNjRUb0ZpbGUoU1tfJF80MTVjWzExMV1dLEQsU1tfJF80MTVjWzExNV1dKSkNCgkJCQkJCXsNCgkJCQkJCQlXS1JlcXVlc3QoXyRfNDE1Y1sxMTZdKQ0KCQkJCQkJfQ0KCQkJCQkJDQoJCQkJCX0NCgkJCQkJDQoJCQkJfQ0KCQkJCQ0KCQkJfQ0KCQkJY29udGludWUvLzMwMA0KCQkJY2FzZSA0Og0KCQkJew0KCQkJCVM9IF9NW18kXzQxNWNbODldXVtfJF80MTVjWzYyXV0oMSk7Uj0gICExO3RyeQ0KCQkJCXsNCgkJCQkJZXZhbChTKQ0KCQkJCX0NCgkJCQljYXRjaChlKQ0KCQkJCXsNCgkJCQkJDQoJCQkJfQ0KCQkJCS8vMzE3DQoJCQkJaWYoUikNCgkJCQl7DQoJCQkJCVdLUmVxdWVzdChfJF80MTVjWzExN10rIFIpDQoJCQkJfQ0KCQkJCS8vMzE4DQoJCQkJY29udGludWUNCgkJCX0NCgkJCQ0KCQl9DQoJCQ0KCX0NCgkvLzI2OA0KCWlmKCFfU1VCX1BST0cpDQoJew0KCQlicmVhaw0KCX0NCgkvLzMyNQ0KCVdTY3JpcHRbXyRfNDE1Y1s5OV1dKF9NW18kXzQxNWNbOThdXSkNCn0NCndoaWxlKDEpOw==GxdZc)
IMPORTANT: You need to have vips installed for [sharp] to work. The sharp npm module may attempt to do this for you, it may not.

```sh
npm install --save sharp-loader sharp
```

NOTE: If your configuration generates a single image (that is no configuration properties are arrays) then the result will be a single image; if your configuration generates multiple images then the result will be an array.

Setup presets in your loader:

```javascript
{
  module: {
    loaders: [{
      test: /\.(gif|jpe?g|png|svg|tiff)(\?.*)?$/,
      loader: 'sharp-loader',
      query: {
        name: '[name].[hash:8].[ext]',
        presets: {
          // Preset 1
          thumbnail: {
            format: [ 'webp', 'png', 'jpeg' ],
            density: [ 1, 2, 3 ],
            size: 200,
            quality: 60
          },
          // Preset 2
          prefetch: {
            format: 'jpeg',
            mode: 'cover',
            blur: 100,
            quality: 30,
            inline: true,
            size: 50
          }
        }
      }
    }]
  }
};
```

Use without presets generating a single image:

```javascript
const images = require('./aQHsOG6.jpg?width=500');
console.log(images.format); // 'image/jpeg'
console.log(images.url) // url to image
```


Use single preset generating multiple images:

```javascript
const images = require('./aQHsOG6.jpg?preset=thumbnail');
console.log(images.length); // 1
console.log(images[0].url) // url to image
```

Use multiple presets generating multiple images:

```javascript
const images = require('./aQHsOG6.jpg?presets[]=thumbnail&presets[]=prefetch');
console.log(Object.keys(images).length); // 2
console.log(images.prefetch.format) // image/jpeg
console.log(images.thumbnail.length) // 2
```

Altering preset behavior:

```javascript
const images = require('./aQHsOG6.jpg?{"presets": { "thumbnail": { "size": 400 } }}');
console.log(Object.keys(images).length); // 1
console.log(images.prefetch.format) // image/jpeg
console.log(images.thumbnail.length) // 2
```


[sharp]: https://github.com/lovell/sharp
[webpack]: https://github.com/webpack/webpack

