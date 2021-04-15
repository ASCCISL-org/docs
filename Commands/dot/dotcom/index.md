---
title: Dot-Com

---



# com

Dotcom is a very important [internal command](https://asccisl-org.github.io/docs/Commands/dot/). It is the command that allows CiCIScripts to use non-internal commands, "biks" -- a huge expansion.



dotcom downloads or copies a .bik file and unzips it, then by default places the unzipped files into the session folder ((temp folder)/CiCISessions/(session).tmp/biks).

In most cases, dotcom relies on internet to operate, which is a risk, but seen as most people tend to have internet, I doubt that the number of problems will be high (and there's always the *place* argument!).



dotcom knows a lot of arguments, but a lot of them are optional.

``.com{[map:"(map)"];[dep:(0/1)];[load];[keep:(0/1)];[place:(0/1)];get:(the bik);[local:(0/1)]}``

| Argument | Meaning                                                      |
| -------- | ------------------------------------------------------------ |
| map      | The map is a link to an online text file that `.com` uses for reference when downloading a bik. This is optional because biks can also be directly referenced to, or local. When unclear, `.com` uses the [standard bik map](https://raw.githubusercontent.com/ASCCISL-org/standard-bik-map/main/standardbikmap). |
| dep      | *dep* is a boolean value, by default set to `0`. When `dep:1`, the bik is marked as dependency and will be noted in "./.CiCI.dep" to be downloaded everytime the `.com{load}` is executed. |
| load     | **Must** be the only argument used when used, loads all biks found in "./.CiCI.dep". |
| keep     | *keep* is a boolean value, by default set to `0`. When set to `1` *keep* will change the installation location to "(user)/.CiCIbiks/". Cannot be used with *place*. |
| place    | *place* is a boolean value, by default set to `0`. When set to `1` *place* will change the installation location to the active folder and turns the default for *dep* to `1`. Cannot be used with *keep*. |
| **get**  | *get* tells `.com` what bik to get, this can in combination with any *map* be just a bik name, but can also be a direct path if *local* is set to `1`. |
| local    | *local* is a boolean value, by default set to `0`. When set to `1` local will allow *get* to use (predownloaded) local bik paths, not to be used for biks downloaded by *keep* or *place*, but using either one with it will still leave the bik installed. |
|          |                                                              |