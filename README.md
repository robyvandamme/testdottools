# dot Tools Tests

## dotADR

Upgrade to the latest version:

```shell
dotnet tool update dotADR --prerelease
```

NOTE: Always commit the version update separately.

### What do we want to test?

* Init use overwrite and init a different directory for every test?
* Add: pick one of the examples in the readme
* Add with supersede: example in the readme

So.....

```shell
dotnet dotadr init -d ./test/doc/adr -o true --debug true --logfile log.txt
```

```shell
dotnet dotadr add "Implement Circuit Breaker Pattern for External Service Calls" --debug true --logfile log.txt
```

```shell
dotnet dotadr add "Separate Read and Write Data Models" -s 002 --debug true --logfile log.txt
```

Review. If it looks good commit it for reference. Then revert the commit? So we can run the same thing and essentially just script it....


