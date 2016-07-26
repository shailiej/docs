+++
date = "2016-07-03T04:02:20Z"
title = "Replicated Private Registry"
description = "How to push and access private images in Replicated's hosted private registry."
weight = "104"
categories = [ "Getting Started" ]

[menu.main]
Name       = "Replicated Private Registry"
identifier = "replicated-private-registry"
parent     = "/getting-started"
url        = "/docs/getting-started/replicated-private-registry"
+++

When building your application, you have the option of hosting your private images on the Replicated private registry.

## Tagging Images

The first thing you will need to do is tag your image. Replicated accepts images in the standard Docker format: `registry.replicated.com/<application-slug>/<image-name>:<version>`. You can find your application slug on the Images tab of the [Replicated Vendor Portal](https://vendor.replicated.com/).

An example of tagging an existing image is:

```shell
$ sudo docker tag myapp/worker registry.replicated.com/mycounterapp/worker:1.0.1
```

## Logging In

Next you will need to log into the Replicated private registry with your Vendor account credentials. When prompted, you will use your email address for both your username.

```shell
$ sudo docker login registry.replicated.com
Username: john@replicated.com
Password: <your password>
Login Succeeded
```

## Pushing Images

Finally you can push your image to the Replicated private registry.

```shell
$ sudo docker push registry.replicated.com/mycounterapp/worker:1.0.1
The push refers to a repository [registry.replicated.com/mycounterapp/worker] (len: 1)
Sending image list
Pushing repository registry.replicated.com/mycounterapp/worker (1 tags)
07595b42e5d5: Image successfully pushed
f9910c2fd14a: Image successfully pushed
4f409c5d1046: Image successfully pushed
8e471642d573: Image successfully pushed
Pushing tag for rev [8e471642d573] on {https://registry.replicated.com/v1/repositories/mycounterapp/worker/tags/1.0.1}
```

For additional information on building, tagging and pushing docker images, please refer to the
[Docker CLI Documentation](https://docs.docker.com/reference/commandline/cli/).