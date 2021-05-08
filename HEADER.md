# **EuroPool . FARM**

First European Chia Farming Pool.

**POOL SHOULD BE ACTIVE 17th MAY WHEN POOLS ARE ENABLED**

Important informations:

- Full Node: `node.europool.farm`
- Donate CHIA: `xch1fqdpju6z6lp48nj8h8g93gwd8xv2jygwuk2wv4kwhnhke0549hps0qu2gt`

# FAQ & TIPS

## Connections troubles

If you don't have connections, check you port (8444) is open: [Port Checker](https://www.yougetsignal.com/tools/open-ports/).

## Maximize space on the disk (plotting and farming)

If you use ext4 (or ext3) filesystem decrease number of inodes:
```
sudo mkfs.ext4 -T largefile4 /dev/sdXX
```
This saves more than 150GB per 10TB drive.

And decrease reserved space for root (to 0%):
```
sudo tune2fs -m 0 /dev/sdXX
```

## Maximize space on temp (plotting) drive

This is still experimental (report back if you tried as well).

You can use btrfs filesystem with lzo compression and mount it with forced compression:

```
mount -o compress-force=lzo /dev/sdXX /XX/temp
```

## Plotting

For effective CLI plotting, use Swar:
[Swar Chia Plot Manager](https://github.com/swar/Swar-Chia-Plot-Manager). Simplest to use plotting tool (that didn't killed any of my plot processes like Chia GUI). It reads `config.yml` live and changes behaviour according. Read more on the project Github page.

```
python manager.py start
python manager.py restart
```
**Restart will not stop your plotting and is needed when large config change is done.**

For status use:
```
python manager.py view
```
It produces output similar to this one:
```
==============================================================================================================================
num   job    k     pid           start          elapsed_time   phase            phase_times            progress   temp_size
==============================================================================================================================
1     ssd    32   38890   2021-05-07 14:50:15   23:18:48       3       13:28 / 04:43                   75.59%     171 GiB
2     ssd    32   59081   2021-05-07 16:30:34   21:38:29       3       13:19 / 04:54                   67.99%     191 GiB
3     ssd    32   20197   2021-05-07 21:51:13   16:17:50       3       08:44 / 04:55                   65.41%     192 GiB
4     ssd    32   25836   2021-05-07 23:31:37   14:37:26       3       08:13 / 05:00                   59.35%     211 GiB
5     ssd    32   48693   2021-05-08 01:11:56   12:57:07       2       08:06                           52.59%     228 GiB
6     ssd    32   6538    2021-05-08 02:52:14   11:16:49       2       08:02                           49.50%     195 GiB
7     ssd    32   26473   2021-05-08 04:32:30   09:36:33       2       08:12                           41.45%     171 GiB
8     ssd    32   48835   2021-05-08 06:12:45   07:56:17       1                                       31.36%     162 GiB
9     ssd    32   8003    2021-05-08 07:53:01   06:16:02       1                                       24.73%     166 GiB
10    ssd    32   28370   2021-05-08 09:33:18   04:35:45       1                                       19.06%     161 GiB
11    ssd    32   48754   2021-05-08 11:13:35   02:55:28       1                                       13.26%     145 GiB
12    ssd    32   1270    2021-05-08 12:53:51   01:15:12       1                                       7.05%      94 GiB
13    ssd    32   7228    2021-05-07 13:00:52   01:08:11       3       13:24 / 04:47                   84.88%     147 GiB
14    root   32   56409   2021-05-06 13:07:11   01:01:52       5       17:05 / 07:03 / 22:44 / 01:00   100.00%    101 GiB
==============================================================================================================================
Manager Status: Running

==========================================================================
type             drive                used     total    percent   plots
==========================================================================
temp   /home/user/ssd/work/chia   2.19TiB   2.95TiB   74.9%     ?
temp   /home/user/work/chia       0.15TiB   0.48TiB   32.5%     ?
dest   /home/user/hdd/work/chia   4.53TiB   4.96TiB   92.2%     ?
==========================================================================
CPU Usage: 28.2%
RAM Usage: 29.30/62.91GiB(47.7%)

Plots Completed Yesterday: 8
Plots Completed Today: 10

Next log check at 2021-05-08 14:10:03
```

# POOLING INFO

Chia Key Architecture:
[Chia Network Github](https://github.com/Chia-Network/chia-blockchain/wiki/Chia-Keys-Architecture). Explains how pools will work.

# DONATE

- Donate CHIA: `xch1fqdpju6z6lp48nj8h8g93gwd8xv2jygwuk2wv4kwhnhke0549hps0qu2gt`
