# no cow

```text
             count = 10000000
         mean rate = 12893.04 calls/second
     1-minute rate = 13161.90 calls/second
     5-minute rate = 12876.27 calls/second
    15-minute rate = 12366.75 calls/second
               min = 0.47 milliseconds
               max = 6.86 milliseconds
              mean = 0.75 milliseconds
            stddev = 0.29 milliseconds
            median = 0.69 milliseconds
              75% <= 0.79 milliseconds
              95% <= 1.05 milliseconds
              98% <= 1.40 milliseconds
              99% <= 1.73 milliseconds
            99.9% <= 4.07 milliseconds
```

## Cow

```text
stats-per-run-INSERT
2020-05-12 14:16:52,711 [main] INFO  d.i.mongodb.perf.MongoDbAccessor - <<< closeConnections mongodb.mongodb:27017
             count = 1000000
         mean rate = 13484.97 calls/second
     1-minute rate = 13279.02 calls/second
     5-minute rate = 12849.60 calls/second
    15-minute rate = 12738.11 calls/second
               min = 0.48 milliseconds
               max = 2.12 milliseconds
              mean = 0.72 milliseconds
            stddev = 0.16 milliseconds
            median = 0.69 milliseconds
              75% <= 0.78 milliseconds
              95% <= 1.00 milliseconds
              98% <= 1.13 milliseconds
              99% <= 1.35 milliseconds
            99.9% <= 2.08 milliseconds
```

## Test

```text
export jarfile=./latest-version/mongodb-performance-test.jar
cd mongodb-performance-test/
java -jar $jarfile -m insert -o 1000000 -t 10 -db test -c perf -h mongodb.mongodb -port 27017 -u root -p 'Password1' -adb admin -s 10000
```

## 2.5.1.1 threads:32-24-32

```text
             count = 1000000
         mean rate = 5171.81 calls/second
     1-minute rate = 4786.62 calls/second
     5-minute rate = 5592.03 calls/second
    15-minute rate = 5900.28 calls/second
               min = 1.07 milliseconds
               max = 9.97 milliseconds
              mean = 1.78 milliseconds
            stddev = 0.53 milliseconds
            median = 1.67 milliseconds
              75% <= 1.90 milliseconds
              95% <= 2.45 milliseconds
              98% <= 2.99 milliseconds
              99% <= 4.44 milliseconds
            99.9% <= 6.23 milliseconds
```

## 2.5.1.1 threads:16-12-16

```text
             count = 1000000
         mean rate = 4870.89 calls/second
     1-minute rate = 5103.15 calls/second
     5-minute rate = 3999.46 calls/second
    15-minute rate = 3458.86 calls/second
               min = 1.15 milliseconds
               max = 6.75 milliseconds
              mean = 1.79 milliseconds
            stddev = 0.56 milliseconds
            median = 1.66 milliseconds
              75% <= 1.89 milliseconds
              95% <= 2.58 milliseconds
              98% <= 3.40 milliseconds
              99% <= 4.26 milliseconds
            99.9% <= 6.75 milliseconds
```

## 2.5.1.1 repl-2, threads: 16-12-16

```text
             count = 1000000
         mean rate = 4173.56 calls/second
     1-minute rate = 4167.40 calls/second
     5-minute rate = 4458.40 calls/second
    15-minute rate = 4651.99 calls/second
               min = 1.12 milliseconds
               max = 635.90 milliseconds
              mean = 3.87 milliseconds
            stddev = 32.23 milliseconds
            median = 1.68 milliseconds
              75% <= 1.98 milliseconds
              95% <= 3.70 milliseconds
              98% <= 5.05 milliseconds
              99% <= 6.27 milliseconds
            99.9% <= 635.90 milliseconds
```

## 2.5.1.1 repl-2, threads: 32.24-36

```text
             count = 1000000
         mean rate = 4676.24 calls/second
     1-minute rate = 4635.36 calls/second
     5-minute rate = 4957.78 calls/second
    15-minute rate = 5142.79 calls/second
               min = 1.11 milliseconds
               max = 262.03 milliseconds
              mean = 2.14 milliseconds
            stddev = 8.82 milliseconds
            median = 1.65 milliseconds
              75% <= 1.97 milliseconds
              95% <= 3.06 milliseconds
              98% <= 4.07 milliseconds
              99% <= 4.72 milliseconds
            99.9% <= 262.03 milliseconds
```

## 3.0-ea1

```text
             count = 1000000
         mean rate = 4865.61 calls/second
     1-minute rate = 4811.45 calls/second
     5-minute rate = 5418.57 calls/second
    15-minute rate = 5786.07 calls/second
               min = 1.02 milliseconds
               max = 16.07 milliseconds
              mean = 1.47 milliseconds
            stddev = 0.62 milliseconds
            median = 1.37 milliseconds
              75% <= 1.54 milliseconds
              95% <= 1.88 milliseconds
              98% <= 2.24 milliseconds
              99% <= 3.68 milliseconds
            99.9% <= 11.12 milliseconds

```

## gcp pd-ssd

```text
             count = 1000000
         mean rate = 2532.95 calls/second
     1-minute rate = 1787.98 calls/second
     5-minute rate = 3284.28 calls/second
    15-minute rate = 4684.51 calls/second
               min = 1.04 milliseconds
               max = 987.43 milliseconds
              mean = 5.89 milliseconds
            stddev = 58.26 milliseconds
            median = 1.44 milliseconds
              75% <= 1.60 milliseconds
              95% <= 2.03 milliseconds
              98% <= 3.27 milliseconds
              99% <= 5.05 milliseconds
            99.9% <= 987.43 milliseconds
```
