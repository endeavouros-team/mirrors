# Mirrors for EndeavourOS repos
[![Maintenance](https://img.shields.io/maintenance/yes/2023.svg)]()

## want to add a mirror?
We welcome any expansion of our mirror servers around the world. 
It is our pleasure to add your mirror to the list. For all further information see here:
https://raw.githubusercontent.com/endeavouros-team/mirrors/master/how-to-add-mirror


[Latest up-to-date endeavouros-mirrorlist](https://gitlab.com/endeavouros-filemirror/PKGBUILDS/-/raw/master/endeavouros-mirrorlist/endeavouros-mirrorlist)

```
######################################################
####                                              ####
###        EndeavourOS Repository Mirrorlist       ###
####                                              ####
######################################################
#### Entry in file /etc/pacman.conf:
###     [endeavouros]
###     SigLevel = PackageRequired
###     Include = /etc/pacman.d/endeavouros-mirrorlist
######################################################
### Tip: Use the 'eos-rankmirrors' program to rank
###      these mirrors or re-order them manually.
######################################################

## Canada
Server = https://ca.gate.endeavouros.com/endeavouros/repo/$repo/$arch

## China
Server = https://mirrors.tuna.tsinghua.edu.cn/endeavouros/repo/$repo/$arch

## Germany
Server = https://mirror.alpix.eu/endeavouros/repo/$repo/$arch
Server = https://de.freedif.org/EndeavourOS/repo/$repo/$arch
Server = https://mirror.moson.org/endeavouros/repo/$repo/$arch

## France
Server = https://endeavour.remi.lu/repo/$repo/$arch
Server = https://mirror.jordanrey.me/endeavouros/repo/$repo/$arch

## India
Server = https://mirror.albony.xyz/endeavouros/repo/$repo/$arch

## Moldova
Server = https://md.mirrors.hacktegic.com/endeavouros/repo/$repo/$arch

## Singapore
Server = https://mirror.jingk.ai/endeavouros/repo/$repo/$arch
Server = https://mirror.freedif.org/EndeavourOS/repo/$repo/$arch

## South Korea
Server = https://mirror.funami.tech/endeavouros/repo/$repo/$arch

## Sweden
Server = https://ftp.acc.umu.se/mirror/endeavouros/repo/$repo/$arch
Server = https://mirror.linux.pizza/endeavouros/repo/$repo/$arch

## Taiwan
Server = https://mirror.archlinux.tw/EndeavourOS/repo/$repo/$arch

## Ukraine
Server = https://fastmirror.pp.ua/endeavouros/repo/$repo/$arch

## United States
Server = https://mirrors.gigenet.com/endeavouros/repo/$repo/$arch
```

## Default EndeavourOS `pacman.conf`
To update from older installs:
```
wget https://raw.githubusercontent.com/endeavouros-team/EndeavourOS-ISO/main/airootfs/etc/pacman.conf && sudo cp pacman.conf /etc/
```
```
#
# /etc/pacman.conf
#
# See the pacman.conf(5) manpage for option and repository directives

#
# GENERAL OPTIONS
#
[options]
# The following paths are commented out with their default values listed.
# If you wish to use different paths, uncomment and update the paths.
#RootDir     = /
#DBPath      = /var/lib/pacman/
#CacheDir    = /var/cache/pacman/pkg/
#LogFile     = /var/log/pacman.log
#GPGDir      = /etc/pacman.d/gnupg/
#HookDir     = /etc/pacman.d/hooks/
HoldPkg     = pacman glibc
#XferCommand = /usr/bin/curl -L -C - -f -o %o %u
#XferCommand = /usr/bin/wget --passive-ftp -c -O %o %u
#CleanMethod = KeepInstalled
#UseDelta    = 0.7
Architecture = auto

# Pacman won't upgrade packages listed in IgnorePkg and members of IgnoreGroup
#IgnorePkg   =
#IgnoreGroup =

#NoUpgrade   =
#NoExtract   =

# Misc options
#UseSyslog
Color
ILoveCandy
#NoProgressBar
#CheckSpace
VerbosePkgLists
DisableDownloadTimeout
ParallelDownloads = 10

# By default, pacman accepts packages signed by keys that its local keyring
# trusts (see pacman-key and its man page), as well as unsigned packages.
SigLevel    = Required DatabaseOptional
LocalFileSigLevel = Optional
#RemoteFileSigLevel = Required

# NOTE: You must run `pacman-key --init` before first using pacman; the local
# keyring can then be populated with the keys of all official Arch Linux
# packagers with `pacman-key --populate archlinux`.

#
# REPOSITORIES
#   - can be defined here or included from another file
#   - pacman will search repositories in the order defined here
#   - local/custom mirrors can be added here or in separate files
#   - repositories listed first will take precedence when packages
#     have identical names, regardless of version number
#   - URLs will have $repo replaced by the name of the current repo
#   - URLs will have $arch replaced by the name of the architecture
#
# Repository entries are of the format:
#       [repo-name]
#       Server = ServerName
#       Include = IncludePath
#
# The header [repo-name] is crucial - it must be present and
# uncommented to enable the repo.
#

# The testing repositories are disabled by default. To enable, uncomment the
# repo name header and Include lines. You can add preferred servers immediately
# after the header, and they will be used before the default mirrors.

#[testing]
#Include = /etc/pacman.d/mirrorlist

[endeavouros]
SigLevel = PackageRequired
Include = /etc/pacman.d/endeavouros-mirrorlist

[core]
Include = /etc/pacman.d/mirrorlist

[extra]
Include = /etc/pacman.d/mirrorlist

#[community-testing]
#Include = /etc/pacman.d/mirrorlist

[community]
Include = /etc/pacman.d/mirrorlist

# If you want to run 32 bit applications on your x86_64 system,
# enable the multilib repositories as required here.

#[multilib-testing]
#Include = /etc/pacman.d/mirrorlist

[multilib]
Include = /etc/pacman.d/mirrorlist

# An example of a custom package repository.  See the pacman manpage for
# tips on creating your own repositories.
#[custom]
#SigLevel = Optional TrustAll
#Server = file:///home/custompkgs

```
