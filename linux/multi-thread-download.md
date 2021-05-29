# Multi-thread download

In Ubuntu, the alternative to IDM is aria2. So:

```bash
sudo apt-get install aria2
```

And then read the documentation on how to use. A simple usage is:

```bash
# Download with 3 connections per host
aria2c -x3 <file_link>
```

