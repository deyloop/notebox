# isosec as KEG node identifier

***Advantages***

For a single user with multiple `keg`s, it is easy to move a node from
one `keg` to the other because it is impossible for one persone to
generate the same node id, regardless of where they generate it. (unless
they write two `keg` nodes within the same second.)

All ids generated will have the same width in terms of characters, at
least for a long long time. (isosecs will gain an additional digit in
the year 10,000)

***Disadvantages***

It is hard to generate several isosec ids as a sequence in a batch
programatically, since you would have to wait for 1 second between each
id being generated. If you simply increment the ids and not wait for the
1 second, the isosecs loose thier meaning and then we will also have to
keep track of the last isosec generated, so if that last id is later
than the isosec representation of now, we will have to be carefull since
now there can be id collisions.

