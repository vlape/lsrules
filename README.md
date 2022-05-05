# lsrules
My Little Snitch Rules

[Reference](https://help.obdev.at/littlesnitch4/ref-lsrules-file-format)

A simple example

Let’s start with a simple example that specifies a single rule for allowing software updates for LaunchBar:

```
{
  "name": "LaunchBar Software Update",
  "description": "This rule allows LaunchBar to check for updates.",
  "rules":
  [
    {
      "action": "allow",
      "process": "/Applications/LaunchBar.app/Contents/MacOS/LaunchBar",
      "remote-hosts": "sw-update.obdev.at"
    }
  ]
}
```


Blocklists

A common use case for rule group subscriptions are blocklists that contain a lot of domains, hosts, or IP addresses for which access should be flat out denied. Using the above syntax, you’d have to repeat "process": "any" and "action": "deny" for each domain, host, or IP address. For thousands of rules, that can lead to unnecessarily large files that in turn lead to unnecessarily large downloads for every single subscriber.

Starting in Little Snitch 4.2, you can use a more compact format that looks like this:

```
{
"name": "Social Media Block List",
"description": "Blocks access to popular social media sites.",
"denied-remote-domains": ["facebook.com", "twitter.com", "youtube.com"]
}
```