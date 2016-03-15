# Introduction #

This is an implementation of the FNV Hash (Fowler-Noll-Vo hash function) algorithm written in PHP.

Fowler/Noll/Vo is a non-cryptographic hash function created by Glenn Fowler, Landon Curt Noll, and Phong Vo. The current versions are FNV-1 and FNV-1a, which supply a means of creating non-zero FNV offset basis. FNV currently comes in 32-, 64-, 128-, 256-, 512-, and 1024-bit flavors. For pure FNV implementations, this is determined solely by the availability of FNV primes for the desired bit length; however, the FNV webpage discusses methods of adapting one of the above versions to a smaller length that may or may not be a power of two.

More information about the Fowler-Noll-Vo hash function could be found here:
  * http://www.isthe.com/chongo/tech/comp/fnv/index.html
  * http://en.wikipedia.org/wiki/Fowler-Noll-Vo_hash_function


# Details #

This is very simple implementation.

FNV is very simple algorithm and produces fairly good results.

I needed this functionality for another project that required automated generation of very large quantities of unique usernames based on limited information provided by the user.

I started with the 32-bit hash version of this algorithm.

According to the Noll's website the core of the FNV-1 hash algorithm is as follows:
```
 hash = offset_basis
 for each octet_of_data to be hashed
   hash = hash * FNV_prime
   hash = hash xor octet_of_data
 return hash
```

I found very nice Java implementation on Andrzej Bialecki (http://www.getopt.org/) website. Here is a fragment of it:
```
 long fnv(byte[] buf, int offset, int len, long seed)
 {
   for (int i = offset; i < offset + len; i++)
   {
     seed += (seed << 1) + (seed << 4) + (seed << 7) + (seed << 8) + (seed << 24);
     seed ^= buf[i];
   }
   return seed;
 }
```

Here is a fragment from the PHP implementation as well:
```
 $buf = str_split($txt);
 $hash = FNV_offset_basis_32;
 foreach ($buf as $chr)
 {
   $hash += ($hash << 1) + ($hash << 4) + ($hash << 7) + ($hash << 8) + ($hash << 24);
   $hash = $hash ^ ord($chr);
 }
 $hash = $hash & 0x0ffffffff;
```
Please look at the source repository for the most recent code.


# Challenges #

The PHP doesn't seam to work very well with numbers. I spent hours trying to figure out why my implementation did not work, i.e. not producing correct results, realizing in the end that multiplying large number is not among PHP's strengths.

To resolve these issues I used "bitwise shift" and "add" operations instead of multiplying by large unumbers:
```
 $hash += ($hash << 1) + ($hash << 4) + ($hash << 7) + ($hash << 8) + ($hash << 24);
```
This should improve the performance as well.


# Repository #

Get a local copy of the boyanov prototypes repository with this command:
> hg clone https://prototypes.boyanov.googlecode.com/hg/ boyanov-prototypes

Direct browsing:
> http://code.google.com/p/boyanov/source/browse/?repo=prototypes#hg/fnvhash


# Screenshots #

People love to see screenshots, even for things as simple as algorithms, so here it is one:

![http://prototypes.boyanov.googlecode.com/hg/fnvhash/fnvhash-270x172s.png](http://prototypes.boyanov.googlecode.com/hg/fnvhash/fnvhash-270x172s.png)