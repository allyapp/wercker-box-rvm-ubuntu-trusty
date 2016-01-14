# Ally's Main Wercker Ubuntu Trusty + RVM Box

[![wercker status](https://app.wercker.com/status/a104f99bb9e073d8777f1c37fc13c453/m "wercker status")](https://app.wercker.com/project/bykey/a104f99bb9e073d8777f1c37fc13c453)

## How to update included Ruby versions

In the packages list, add the required Ruby:

```
packages:
	...
	- ruby@2.3.0
	- ruby@2.4.0
```

In the script install that Ruby and make it the default one:

```
script: |
	...
	rvm install 2.3.0
	rvm install 2.4.0
	rvm --default use 2.4.0
```

Also see the exemplary PR for those required changes here:
https://github.com/allyapp/wercker-box-rvm-ubuntu-trusty/pull/1

With these changes pushed to master and built on Wercker, make the updated box available in Wercker's registry
by deploying the box from Wercker to the (only) deploy target named "registry", from:
https://app.wercker.com/#applications/56967ee755813dda3b03e540


Any new build that is using this box will automatically use Ruby 2.4.0 from then on.
