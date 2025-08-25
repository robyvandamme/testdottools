# dotTools Tests

## Preparation

Make sure the correct .NET SDK is installed or adapt the global.json to match an installed version on the machine:

```shell
dotnet --list-sdks
```

When testing private packages make sure the relevant environment variables are configured on the host machine:

```xml

	<packageSourceCredentials>
		<robyvandamme>
			<add key="Username" value="%GITHUB_PACKAGES_USER%" />
			<add key="ClearTextPassword" value="%GITHUB_PACKAGES_TOKEN%" />
		</robyvandamme>
	</packageSourceCredentials> 

```

Restore the tools:

```shell
dotnet tool restore
````

## dotADR

Upgrade to the latest version:

```shell
dotnet tool update dotADR --prerelease
```

NOTE: Always commit the tool version update separately.

### Test


```shell
dotnet dotadr init -d ./test/doc/adr -o true --debug true --logfile log.txt
```

```shell
dotnet dotadr add "Implement Circuit Breaker Pattern for External Service Calls" --debug true --logfile log.txt
```

```shell
dotnet dotadr add "Separate Read and Write Data Models" -s 002 --debug true --logfile log.txt
```

Review. If it looks good commit it for reference. Then revert the commit.

Commit message: 

```text
test: {OS} test dotADR {version}
```

## Linux 

Use devcontainers. Configured and tested.

## Windows

Use AWS EC2 - t3.medium - $0.0712 - 2 vCPU - 4 GiB - EBS Only - Up to 5 Gigabit

