### Install Plugin
`$ curl -o /usr/share/munin/plugins/bitcoind_ https://raw.githubusercontent.com/MorbZ/munin-bitcoind/master/bitcoind_`  
`$ chmod +x /usr/share/munin/plugins/bitcoind_`  

Create file `/etc/munin/plugin-conf.d/bitcoind` with contents:

    [bitcoind_*]
    user root

`$ mkdir /.bitcoin`  
`$ cp ~/.bitcoin/bitcoin.conf /.bitcoin`  

### Setup Graphs
Number of connections:  
`$ ln -s /usr/share/munin/plugins/bitcoind_ /etc/munin/plugins/bitcoind_connections`

Block count:  
`$ ln -s /usr/share/munin/plugins/bitcoind_ /etc/munin/plugins/bitcoind_blocks`

Difficulty:  
`$ ln -s /usr/share/munin/plugins/bitcoind_ /etc/munin/plugins/bitcoind_difficulty`

Don't forget to restart Munin after changing plugins:  
`$ service munin-node restart`