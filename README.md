# munin-speedtest-plugin
A Munin plugin to graph the results from speedtest-cli

Setup instructions:

1. Download [speedtest-cli](https://github.com/sivel/speedtest-cli)

  ```bash
  wget -O speedtest-cli https://raw.github.com/sivel/speedtest-cli/master/speedtest_cli.py
  chmod +x speedtest-cli
  ```
1. Create a crontab similar to this

  ```bash
  crontab -e
  58,18,38 * * * * root /<path>/<to>/<file>/speedtest-cli --simple > /tmp/speedtest.out
  ```
1. Copy speedtest.sh into Munin plugins folder (on Debian/Ubuntu)

  ```bash
  cp /<path>/<to>/<file>/speedtest.sh /etc/munin/plugins/speedtest.sh
  chmod 777 /etc/munin/plugins/speedtest.sh
  ```
1. Restart munin-node to detect the new plugin

  ```bash
  sudo /etc/init.d/munin-node restart
  ```

Original author: Alex Pardoe

Monitoring Internet Connection Speed With Munin<br>
http://www.pardoe.io/blog/2013/04/29/monitoring-internet-connection-speed-with-munin

Github Gist - speedtest-cli.sh<br>
https://gist.github.com/digitalpardoe/5481339
