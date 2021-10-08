---
layout: page
title: SSH Tunnel to a DSMLP Container
doodle: /assets/images/doodle.png
---

This article will discuss how to connect to a Jupyter Notebook instance on DSMLP without using the campus VPN.

## Why do we need SSH tunneling

On `datahub.ucsd.edu`, the familiar Jupyter Notebook interface is automatically available to you. But when you ssh to DSMLP, there is only a link to the Jupyter Notebook url, and you would have to connect to the campus VPN beforehand to actually have access to that url. There exists another way to connect to the Jupyter interface without the hassle of connecting to the VPN, while also being secure. This method works for every OS that has SSH installed, even iOS or Android, though you might not want to develop on a mobile device.

## Connecting Steps

You will need to open two terminal windows/tabs for doing this. One is for launching the container on DSMLP, the other is for port-forwarding the assigned port to your local machine.

In the first terminal, ssh to `dsmlp-login.ucsd.edu` and create a container using any of the launch scripts, you will see a message similar to this:

```
Please connect to: http://dsmlp-login.ucsd.edu:13450/?token=long_string_or_random_numbers_and_characters
```

The number `13450` after the colon is the **port** which you want to "map/forward" onto your local machine.

Open a new terminal on your **local machine** and make sure the prompt is your computer's name, not "dsmlp-login", and use this command

```bash
$ ssh -N -L 8889:127.0.0.1:<port> <user>@dsmlp-login.ucsd.edu
```

Replace `<port>` with the port you see on the terminal and `<user>` with your ucsd AD username, an example would be 

```bash
$ ssh -N -L 8889:127.0.0.1:13450 y3zou@dsmlp-login.ucsd.edu
```

If you don't see any message after you entered the password, you are good to go.

Now go to <http://localhost:8889> on your **local machine**'s browser and you should see a login page prompting you to type in another password. Copy from the message earlier after `token=` and paste it here. Click "login" and now you are in Jupyter.

Alternatively, you can just copy and paste the url earlier and replace `dsmlp-login.ucsd.edu` with `localhost`, and change the port number -- the url pass in the password for you.

If you see a message `channel 2: open failed: connect failed: Connection refused` on your second terminal, you could be entering a wrong port number, so double check that.

## Disconnecting

To disconnect, first stop your Jupyter instance. Either use the **Quit** button on the Jupyter home page or enter exit in your terminal used to launch the container. Switch to the port-mapping terminal, press `Ctrl+C` (same on Windows/Mac) and it will stop the tunneling process.

## Next Steps

### SSH login without typing the password every time

- Read this [article](https://www.digitalocean.com/community/tutorials/how-to-configure-ssh-key-based-authentication-on-a-linux-server) from DigitalOcean.
- Do this for every machine you use to ssh to dsmlp with.

### Port-forward services other than Jupyter

If you launched a container with a different sets of services, like `redis`, there will be an extra step to access the service on your local machine.

When you are launching a standard Datahub container, the launch script does something automatically for you, that is, it uses the [`kubectl`](https://kubernetes.io/docs/tasks/tools/#kubectl) command to [`port-forward`](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#port-forward) the [container port](https://kubernetes.io/docs/concepts/services-networking/connect-applications-service/#exposing-pods-to-the-cluster) out to the "dsmlp-login" Linux server. The reason for this is that the actual nodes (essentially individual computers in a cluster) that your pod is running on, are walled off to the public internet, and the only way to access it is through dsmlp-login.

So, for example we launched a `redis` instance with the container name being `redis-container`. We know that the default port for redis is `6379`, so we will first use the command `kubectl port-forward redis-container :6379`. This is to forward the "container port" `6379` inside to an arbitary port where the command is run, in this case, dsmlp-login.

And then you would go through the steps detailed earlier in the article to port-foward again, this time using SSH.

Repeat these steps for every port you are trying to access.

## Reference

Official docs on using DSMLP command line: https://support.ucsd.edu/services?id=kb_article_view&sys_kb_id=cbb951c31b42a050df40ed7dee4bcb9e