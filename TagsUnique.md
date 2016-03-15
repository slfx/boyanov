# Introduction #

An algorithm that generates unique tags trying to keep the length as small as possible.

# Details #

This algorithm generates tags - unique combination of characters. Example: 4H38 476F 2R9Z 7MB5 2TSM MX6.

The list of allowed characters is defined in the configuration.

The storage used is the file system, there is no need to use a database.

The algorithm should start with smaller length and as the number of generated tags grows the length of the newly generated will increase as well. This allows at the beginning to have shorter

# Reliability #

The algorithm largely relies on rand() function to generate random numbers for the purpose to choose generated characters. In theory it is possible to lock the algorithm, but this could only happen if the function rand() generates at the first round all the unique allowed character without repeating even one. That of course is very unlikely to happen.

There are ways to prevent that. For example, every time we reserve folder ("folder" in the terminology of that algorithm) a sub-folder should be created to ensure that there is "escape" in case all the characters are used out.

# Examples #

Example of generated tags: 4H38 476F 2R9Z 7MB5 2TSM MX6 XX7 6R2J B664 B9J BEH M7S 2TS9 799 BPXK 4H69 M7BH 7ZJ MJ5F XKZF 6MA5 2SN HFME 74SH 6K62 66K7 HES 6R46 6M4 MR4P 44P 27P 2R87 7M3M XD9P HTP XB67 XB4 HFX MEF XXET 4F4 4XB X4D 2R3 X37 47AK 6K7K H6J 7AX 28F 733H 2P96 2KP6 XNEE MKKB 7ZA5 79DF B97Z 2E44 M8RP 2NMS 79TH XAAK HEF 4M8P MXA MRKK 2RR 2KS5 HFE3 746N 47N 4M2A 4E5Z 66MH 6RXT B9B MXD HR4 BEF7 H5DS 6S8 79R XDAP XB8 X3J XT9K 28RB 2NH XXNJ HR8X 2K6N HP9 MRPP XBMS 7M3N 4T78 4ZP 4RX

Note that not all tags are of the same length.

# Applications #

It started with the idea to create an URL shortener library for my Wiki project WiKissMe (http://www.WiKissMe.org). Although it could server other purposes as well.

# Performance #

There is a script that attempts to test the performance of the algorithm.

# Repository #

Get a local copy of the boyanov prototypes repository with this command:
> hg clone https://prototypes.boyanov.googlecode.com/hg/ boyanov-prototypes

Direct browsing:
> http://code.google.com/p/boyanov/source/browse/?repo=prototypes#hg/tagsunique

# Screenshots #

![http://prototypes.boyanov.googlecode.com/hg/tagsunique/tagsunique-328x494.png](http://prototypes.boyanov.googlecode.com/hg/tagsunique/tagsunique-328x494.png)