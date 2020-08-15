# DRAM-RowBuffer-Attack-Detector
DRAM is a resource that is shared even in cloud-based environments where tenants typically do not share CPU or the caches. DRAM access latency depends on row buffer hits and conflicts, thereby opening the ground to carry out side-channel and covert-channel attacks on DRAM. In our project, we proposed a detection technique which detects such side and covert channel attacks on DRAM and mitigated it by using a hybrid open-closed row policy.<br/><br/>
We propose a detection method for side and covert channel attacks on DRAM which detect the attack by keeping a
track of DRAM row conflicts caused by the cores on each other. If two or more cores’ row conflicting values are similar,
we perform two other checks that involve finding similarity between L1 data cache misses of individual conflicting cores
and the last check is to find similarity in conflicting cores’ LLC misses. If any two or more cores pass all of the above
three checks, we declare those cores as active attackers and for such detected cores we follow the closed-row policy where
we return same latency for both, row hit and row miss. This way, the attack is mitigated.
<br/><br/>
I have implemented this project over Champim.
<br/>
To build<br/>
./build_champsim.sh bimodal no no no lru 4
<br/>
To run<br/>
bash run_4core.sh bimodal-no-no-no-lru-4core 0 1 0 set_sender.trace.gz example1.trace.gz example2.trace.gz set_receiver.trace.gz
<br/>
