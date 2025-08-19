# awesome-streaming-graphs
[![Awesome](https://awesome.re/badge.svg)](https://github.com/axtonsun/awesome-streaming-graphs)
![](https://img.shields.io/github/last-commit/axtonsun/awesome-streaming-graphs?color=green) 
![](https://img.shields.io/github/stars/axtonsun/awesome-streaming-graphs)
![](https://img.shields.io/badge/PRs-Welcome-red)

Must-read papers on streaming graph

## [Content](#content)

<table>
<tr><td colspan="2"><a href="#keynote">1. Keynote</a></td></tr> 
<tr><td colspan="2"><a href="#survey-papers">2. Survey</a></td></tr> 
<tr><td colspan="2"><a href="#system">3. System</a></td></tr> 
<tr><td colspan="2"><a href="#streaming-graph-partitioning">4. Streaming Graph Partitioning</a></td></tr> 
<tr><td colspan="2"><a href="#graph-stream-summarization">5. Graph Stream Summarization</a></td></tr> 
<tr><td colspan="2"><a href="#exact-algorithms">6. Exact Algorithms</a></td></tr>
<tr>
    <td>&ensp;<a href="#subgraph-matching">6.1 Subgraph Matching</a></td>
    <td>&ensp;<a href="#regular-path-query">6.2 Regular Path Query</a></td>
</tr>
<tr><td colspan="2"><a href="#approximation-algorithms">7. Approximation Algorithms</a></td></tr>
<tr>
    <td>&ensp;<a href="#triangle-count">7.1 Triangle Count</a></td>
    <td>&ensp;<a href="#butterfly-count">7.2 Butterfly Count</a></td>
</tr>
</table>

## [Keynote](#content)

1. **Streaming Graph Processing and Analytics.** [[slides]](https://cs.uwaterloo.ca/~tozsu/presentations/streaming_graph.pdf) [[DEBS'20 video]](https://www.youtube.com/watch?v=wKJvm_O-Gyc) [[PKUMOD'20 video]](https://www.bilibili.com/video/BV1u54y1S7wj)
   
   *M. Tamer Özsu.* 
   
1. **Graph Processing: A Panaromic View and Some open Problems.** [[slides]](https://cs.uwaterloo.ca/~tozsu/presentations/VLDB19-keynote.pdf) [[VLDB'19 video]](https://www.youtube.com/watch?v=IjChB1tkIrA) [[PKUMOD'20 video]](https://www.bilibili.com/video/BV1QK4y147yz)
   
   *M. Tamer Özsu.* 

1. **An Introduction to Graph Analytics Platform - Very Short Version.** [[slides]](https://cs.uwaterloo.ca/~tozsu/presentations/Graph-analytics-shortest.pdf)
   
   *M. Tamer Özsu.*

## [Survey papers](#content)

1. **Practice of Streaming Processing of Dynamic Graphs: Concepts, Models, and Systems.** IEEE Trans. Parallel Distributed Syst. 34(6): 1860-1876 (2023) [[paper]](https://ieeexplore.ieee.org/document/9629281)
   
   *Maciej Besta, Marc Fischer, Vasiliki Kalavri, Michael Kapralov, Torsten Hoefler.*
   
1. **图数据流的模型、算法和系统[J].** 大数据, 2018, 4(4): 44-55. [[paper]](http://www.infocomm-journal.com/bdr/CN/10.11959/j.issn.2096-0271.2018039)
   
   *李友焕, 邹磊.*  
   
1. **Graph stream algorithms: a survey.** SIGMOD Rec. 43(1): 9-20 (2014) [[paper]](https://doi.org/10.1145/2627692.2627694)
   
   *Andrew McGregor.* 
   
## [System](#content)

1. **GraphGuard: Private Time-Constrained Pattern Detection Over Streaming Graphs in the Cloud.** USENIX Security Symposium 2024 [[paper]](https://www.usenix.org/system/files/usenixsecurity24-wang-songlei.pdf) [[slides]](https://www.usenix.org/system/files/usenixsecurity24_slides-wang-songlei.pdf) [[video]](https://www.youtube.com/watch?v=kftJIwye0ts)

   *Songlei Wang, Yifeng Zheng, Xiaohua Jia.*
   
1. **LSGraph: A Locality-centric High-performance Streaming Graph Engine.** EuroSys 2024: 33-49 [[paper]](https://dl.acm.org/doi/10.1145/3627703.3650076)

   *Hao Qi, Yiyang Wu, Ligang He, Yu Zhang, Kang Luo, Minzhi Cai, Hai Jin, Zhan Zhang, Jin Zhao.*
   
1. **ACGraph: Accelerating Streaming Graph Processing via Dependence Hierarchy.** DAC 2023: 1-6 [[paper]](https://ieeexplore.ieee.org/document/10247904)

   *Zihan Jiang, Fubing Mao, Yapu Guo, Xu Liu, Haikun Liu, Xiaofei Liao, Hai Jin, Wei Zhang.*
   
1. **GeaFlow: A Graph Extended and Accelerated Dataflow System.** Proc. ACM Manag. Data 1(2): 191:1-191:27 (2023) [[paper]](https://dl.acm.org/doi/10.1145/3589771)

   *Zhenxuan Pan, Tao Wu, Qingwen Zhao, Qiang Zhou, Zhiwei Peng, Jiefeng Li, Qi Zhang, Guanyu Feng, Xiaowei Zhu.*
   
1. **GraphFly: Efficient Asynchronous Streaming Graphs Processing via Dependency-Flow.** SC 2022: 45:1-45:14 [[paper]](https://dl.acm.org/doi/10.5555/3571885.3571944)

   *Dan Chen, Chuangyi Gui, Yi Zhang, Hai Jin, Long Zheng, Yu Huang, Xiaofei Liao.*
   
1. **TDGraph: a topology-driven accelerator for high-performance streaming graph processing.** ISCA 2022: 116-129 [[paper]](https://dl.acm.org/doi/10.1145/3470496.3527409)

   *Jin Zhao, Yun Yang, Yu Zhang, Xiaofei Liao, Lin Gu, Ligang He, Bingsheng He, Hai Jin, Haikun Liu, Xinyu Jiang, Hui Yu.*
   
1. **GraphZeppelin: Storage-Friendly Sketching for Connected Components on Dynamic Graph Streams.** SIGMOD Conference 2022: 325-339 [[paper]](https://dl.acm.org/doi/10.1145/3514221.3526146)

   *David Tench, Evan West, Victor Zhang, Michael A. Bender, Abiyaz Chowdhury, J. Ahmed Dellas, Martin Farach-Colton, Tyler Seip, Kenny Zhang.*
   
1. **Controlling Memory Footprint of Stateful Streaming Graph Processing.** USENIX ATC 2021: 269-283 [[paper]](https://www.usenix.org/system/files/atc21-vaziri.pdf) [[sildes]](https://www.usenix.org/system/files/atc21_slides_vaziri.pdf) [[video]](https://www.youtube.com/watch?v=Jg_LRUEbMkc)

   *Pourya Vaziri, Keval Vora.*

1. **RisGraph: A Real-Time Streaming System for Evolving Graphs to Support Sub-millisecond Per-update Analysis at Millions Ops/s.** SIGMOD Conference 2021: 513-527 [[paper]](https://dl.acm.org/doi/10.1145/3448016.3457263)

   *Guanyu Feng, Zixuan Ma, Daixuan Li, Shengqi Chen, Xiaowei Zhu, Wentao Han, Wenguang Chen*

1. **DZiG: sparsity-aware incremental processing of streaming graphs.** EuroSys 2021: 83-98 [[paper]](https://dl.acm.org/doi/10.1145/3447786.3456230)

   *Mugilan Mariappan, Joanna Che, Keval Vora.*

1. **Exploiting Buffered Updates for Fast Streaming Graph Analysis.** IEEE Trans. Computers 70(2): 255-269 (2021) [[paper]](https://ieeexplore.ieee.org/document/9067060)

   *Feng Sheng, Qiang Cao, Jie Yao.*

1. **GraphBolt: Dependency-Driven Synchronous Processing of Streaming Graphs.** EuroSys 2019: 25:1-25:16 [[paper]](https://dl.acm.org/doi/10.1145/3302424.3303974)

   *Mugilan Mariappan, Keval Vora.* 

1. **GraphOne: A Data Store for Real-time Analytics on Evolving Graphs.** FAST 2019: 249-263 [[paper]](https://www.usenix.org/conference/fast19/presentation/kumar) [[slides]](https://www.usenix.org/sites/default/files/conference/protected-files/fast19_slides_kumar.pdf) [[video]](https://www.youtube.com/watch?v=Pqps3bz1LE0) 

   *Pradeep Kumar, H. Howie Huang.*

1. **KickStarter: Fast and Accurate Computations on Streaming Graphs via Trimmed Approximations.** ASPLOS 2017: 237-251 [[paper]](https://dl.acm.org/doi/10.1145/3037697.3037748)

   *Keval Vora, Rajiv Gupta, Guoqing Xu.* 

## [Streaming Graph Partitioning](#content)

1. **Triparts: Scalable Streaming Graph Partitioning to Enhance Community Structure.**  Proc. VLDB Endow. 18(9): 2992 - 3006 (2025) [[paper]](https://www.vldb.org/pvldb/vol18/p2992-simmhan.pdf)

   *Ruchi Bhoot, Tuhin Khare, Manoj Agarwal, Siddharth Jaiswal, Yogesh Simmhan.*
   
1. **CUTTANA: Scalable Graph Partitioning for Faster Distributed Graph Databases and Analytics.**  Proc. VLDB Endow. 18(1): 14-27 (2024) [[paper]](https://www.vldb.org/pvldb/vol18/p14-hajidehi.pdf)

   *Milad Rezaei Hajidehi, Sraavan Sridhar, Margo I. Seltzer.*

1. **Play like a Vertex: A Stackelberg Game Approach for Streaming Graph Partitioning.** Proc. ACM Manag. Data 2(3): 162 (2024) [[paper]](https://doi.org/10.1145/3654965)

   *Zezhong Ding, Yongan Xiang, Shangyou Wang, Xike Xie, S. Kevin Zhou.*

1. **A Mixed-State Streaming Edge Partitioning based on Combinatorial Design.** ICDM 2023: 868-877 [[paper]](https://doi.org/10.1109/ICDM58522.2023.00096)

   *Zhenyu Zhang, Wenwen Qu, Weixi Zhang, Junlin Shang, Xiaoling Wang.*

1. **Lightweight Streaming Graph Partitioning by Fully Utilizing Knowledge from Local View.** ICDCS 2023: 614-625 [[paper]](https://doi.org/10.1109/ICDCS57875.2023.00079)

   *Zhigang Wang, Zichao Yang, Ning Wang, Yujie Du, Jie Nie, Zhiqiang Wei, Yu Gu, Ge Yu.*

1. **Out-of-Core Edge Partitioning at Linear Run-Time.** ICDE 2022: 2629-2642 [[paper]](https://doi.org/10.1109/ICDE53745.2022.00242)

   *Ruben Mayer, Kamil Orujzade, Hans-Arno Jacobsen.*

1. **GCNSplit: bounding the state of streaming graph partitioning.** aiDM@SIGMOD 2022: 3:1-3:12 [[paper]](https://doi.org/10.1145/3533702.3534920) [[code]](https://github.com/CASP-Systems-BU/GCNSplit)

   *Michal Zwolak, Zainab Abbas, Sonia Horchidan, Paris Carbone, Vasiliki Kalavri.*

1. **Quasi-Streaming Graph Partitioning: A Game Theoretical Approach.** IEEE Trans. Parallel Distributed Syst. 30(7): 1643-1656 (2019) [[paper]](https://doi.org/10.1109/TPDS.2018.2890515)

   *Qiang-Sheng Hua, Yangyang Li, Dongxiao Yu, Hai Jin.*

1. **Experimental Analysis of Streaming Algorithms for Graph Partitioning.** SIGMOD Conference 2019: 1375-1392 [[paper]](https://doi.org/10.1145/3299869.3300076) [[code]](https://github.com/anilpacaci/streaming-graph-partitioning)

   *Anil Pacaci, M. Tamer Özsu.*

1. **Streaming Graph Partitioning: An Experimental Study.** Proc. VLDB Endow. 11(11): 1590-1603 (2018) [[paper]](http://www.vldb.org/pvldb/vol11/p1590-abbas.pdf)

   *Zainab Abbas, Vasiliki Kalavri, Paris Carbone, Vladimir Vlassov.*

1. **HDRF: Stream-Based Partitioning for Power-Law Graphs.** CIKM 2015: 243-252 [[paper]](https://doi.org/10.1145/2806416.2806424)

   *Fabio Petroni, Leonardo Querzoni, Khuzaima Daudjee, Shahin Kamali, Giorgio Iacoboni.*

1. **FENNEL: streaming graph partitioning for massive scale graphs.** WSDM 2014: 333-342 [[paper]](https://doi.org/10.1145/2556195.2556213)

   *Charalampos E. Tsourakakis, Christos Gkantsidis, Bozidar Radunovic, Milan Vojnovic.*

1. **Distributed Power-law Graph Computing: Theoretical and Empirical Analysis.** NIPS 2014: 1673-1681 [[paper]](http://papers.nips.cc/paper/5396-distributed-power-law-graph-computing-theoretical-and-empirical-analysis)

   *Cong Xie, Ling Yan, Wu-Jun Li, Zhihua Zhang.*

1. **GraphBuilder: scalable graph ETL framework.** GRADES 2013: 4 [[paper]](http://event.cwi.nl/grades2013/04-jain.pdf)

   *Nilesh Jain, Guangdeng Liao, Theodore L. Willke.*

1. **Streaming graph partitioning for large distributed graphs.** KDD 2012: 1222-1230 [[paper]](https://doi.org/10.1145/2339530.2339722)

   *Isabelle Stanton, Gabriel Kliot.*

1. **PowerGraph: Distributed Graph-Parallel Computation on Natural Graphs.** OSDI 2012: 17-30 [[paper]](https://www.usenix.org/conference/osdi12/technical-sessions/presentation/gonzalez)

   *Joseph E. Gonzalez, Yucheng Low, Haijie Gu, Danny Bickson, Carlos Guestrin.*

## [Graph Stream Summarization](#content)

1. **HourglassSketch: An Efficient and Scalable Framework for Graph Stream Summarization.** ICDE 2025 [[paper]](https://ntguojiarui.github.io/papers/HourglassSketch-ICDE25.pdf) [[code]](https://github.com/HourglassSketch/HourglassSketch-code)

   *Jiarui Guo, Boxuan Chen, Kaicheng Yang, Tong Yang, Zirui Liu, Qiuheng Yin, Sha Wang, Yuhan Wu, Xiaolin Wang, Bin Cui, Tao Li, Xi Peng, Renhai Chen, Gong Zhang.*

1. **HIGGS: HIerarchy-Guided Graph Stream Summarization.** ICDE 2025 [[paper]](https://arxiv.org/abs/2412.15516)

   *Xuan Zhao, Xike Xie, Christian S. Jensen.*

1. **Mayfly: a Neural Data Structure for Graph Stream Summarization.** ICLR 2024 [[paper]](https://openreview.net/pdf?id=n7Sr8SW4bn) [[code]](https://openreview.net/attachment?id=n7Sr8SW4bn&name=supplementary_material)

   *Yuan Feng, Yukun Cao, Hairu Wang, Xike Xie, S. Kevin Zhou.*

1. **Auxo: A Scalable and Efficient Graph Stream Summarization Structure.** Proc. VLDB Endow. 16(6): 1386-1398 (2023) [[paper]](https://www.vldb.org/pvldb/vol16/p1386-chen.pdf)

   *Zhiguo Jiang, Hanhua Chen, Hai Jin.* 

1. **Horae: A Graph Stream Summarization Structure for Efficient Temporal Range Query.** ICDE 2022: 2792-2804 [[paper]](https://doi.org/10.1109/ICDE53745.2022.00254)

   *Ming Chen, Renxiang Zhou, Hanhua Chen, Jiang Xiao, Hai Jin, Bo Li.* 
   
1. **Scube: Efficient Summarization for Skewed Graph Streams.** ICDCS 2022: 100-110 [[paper]](https://doi.org/10.1109/ICDCS54860.2022.00019)

   *Ming Chen, Renxiang Zhou, Hanhua Chen, Hai Jin.*

1. **A parameter-free approach to lossless summarization of fully dynamic graphs.** Inf. Sci. 589: 376-394 (2022) [[paper]](https://doi.org/10.1016/j.ins.2021.12.116)

   *Ziyi Ma, Yuling Liu, ZhiBang Yang, Jianye Yang, Kenli Li.*

1. **A Parameter-Free Approach for Lossless Streaming Graph Summarization.** DASFAA (1) 2021: 385-393 [[paper]](https://doi.org/10.1007/978-3-030-73194-6_26)

   *Ziyi Ma, Jianye Yang, Kenli Li, Yuling Liu, Xu Zhou, Yikun Hu.*

1. **DMatrix: Toward fast and accurate queries in graph stream.** Comput. Networks 198: 108403 (2021) [[paper]](https://doi.org/10.1016/j.comnet.2021.108403) [[code]](https://github.com/houchangsheng/DMatrix)

   *Changsheng Hou, Bingnan Hou, Tongqing Zhou, Zhiping Cai.*

1. **Graph Stream Sketch: Summarizing Graph Streams With High Speed and Accuracy.** IEEE Trans. Knowl. Data Eng. 35(6): 5901-5914 (2023) [[paper]](https://doi.org/10.1109/TKDE.2022.3174570)

   *Xiangyang Gou, Lei Zou, Chenxingyu Zhao, Tong Yang.* 

1. **Fast and Accurate Graph Stream Summarization.** ICDE 2019: 1118-1129 [[paper]](https://doi.org/10.1109/ICDE.2019.00103)

   *Xiangyang Gou, Lei Zou, Chenxingyu Zhao, Tong Yang.* 

1. **Incremental Lossless Graph Summarization.**  KDD 2020: 317-327 [[paper]](https://dl.acm.org/doi/10.1145/3394486.3403074) [[slides]](https://www.slideshare.net/ssuserd6bbc0/incremental-lossless-graph-summarization-kdd-2020) [[video]](https://youtu.be/FHVx642GoaI) 

   *Jihoon Ko, Yunbum Kook, Kijung Shin.* 

1. **Graph Stream Summarization: From Big Bang to Big Crunch.** SIGMOD Conference 2016: 1481-1496 [[paper]](https://dl.acm.org/doi/10.1145/2882903.2915223) [[slides]](https://prezi.com/wj5kw9wbmr8o/tcm/)

   *Nan Tang, Qing Chen, Prasenjit Mitra.*

1. **gSketch: On Query Estimation in Graph Streams.** Proc. VLDB Endow. 5(3): 193-204 (2011) [[paper]](http://www.vldb.org/pvldb/vol5/p193_peixiangzhao_vldb2012.pdf)

   *Peixiang Zhao, Charu C. Aggarwal, Min Wang.*

## [Exact Algorithms](#content) 

### [Subgraph Matching](#content) 

1. **TC-Match: Fast Time-constrained Continuous Subgraph Matching.** Proc. VLDB Endow. 17(11): 2791-2804 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p2791-yang.pdf) [[code]](https://github.com/Sh-Fang/TCMatch)

   *Jianye Yang, Sheng Fang, Zhaoquan Gu, Ziyi Ma, Xuemin Lin, Zhihong Tian.*

1. **CSM-TopK: Continuous Subgraph Matching with TopK Density Constraints.** ICDE 2024: 3084-3097 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00239) [[code]](https://github.com/chuchugao2/CSMTopk)

   *Chuchu Gao, Youhuan Li, Zhibang Yang, Xu Zhou.*

1. **Efficient Multi-Query Oriented Continuous Subgraph Matching.** ICDE 2024: 3230-3243 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00250)

   *Ziyi Ma, Jianye Yang, Xu Zhou, Guoqing Xiao, Jianhua Wang, Liang Yang, Kenli Li, Xuemin Lin.*

1. **Time-Constrained Continuous Subgraph Matching Using Temporal Information for Filtering and Backtracking.** ICDE 2024: 3257-3269 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00252)

   *Seunghwan Min, Jihoon Jang, Kunsoo Park, Dora Giammarresi, Giuseppe F. Italiano, Wook-Shin Han.*

1. **NewSP: A New Search Process for Continuous Subgraph Matching over Dynamic Graphs.** ICDE 2024: 3324-3337 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00257)

   *Ziming Li, Youhuan Li, Xinhuan Chen, Lei Zou, Yang Li, Xiaofeng Yang, Hongbo Jiang.*

1. **Fast Continuous Subgraph Matching over Streaming Graphs via Backtracking Reduction.** Proc. ACM Manag. Data 1(1): 15:1-15:26 (2023) [[paper]](https://dl.acm.org/doi/10.1145/3588695) [[code]](https://github.com/JackChuengQAQ/CaLiG) [[video]](https://dl.acm.org/action/downloadSupplement?doi=10.1145/3588695&file=meeting_09.mp4)

   *Rongjian Yang, Zhijie Zhang, Weiguo Zheng, Jeffrey Xu Yu.*

1. **An In-Depth Study of Continuous Subgraph Matching.** Proc. VLDB Endow. 15(7): 1403-1416 (2022) [[paper]](https://www.vldb.org/pvldb/vol15/p1403-sun.pdf) [[code]](https://github.com/RapidsAtHKUST/ContinuousSubgraphMatching)

   *Xibo Sun, Shixuan Sun, Qiong Luo, Bingsheng He.*

1. **RapidFlow: An Efficient Approach to Continuous Subgraph Matching.** Proc. VLDB Endow. 15(11): 2415-2427 (2022) [[paper]](https://www.vldb.org/pvldb/vol15/p2415-sun.pdf) [[code]](https://github.com/shixuansun/RapidFlow)

   *Shixuan Sun, Xibo Sun, Bingsheng He, Qiong Luo.*

1. **RapidMatch: A Holistic Approach to Subgraph Query Processing.** Proc. VLDB Endow. 14(2): 176-188 (2020) [[paper]](https://www.vldb.org/pvldb/vol14/p176-sun.pdf) [[code]](https://github.com/RapidsAtHKUST/RapidMatch)

   *Shixuan Sun, Xibo Sun, Yulin Che, Qiong Luo, Bingsheng He.*

1. **Symmetric Continuous Subgraph Matching with Bidirectional Dynamic Programming.** Proc. VLDB Endow. 14(8): 1298-1310 (2021) [[paper]](https://www.vldb.org/pvldb/vol14/p1298-han.pdf) [[code]](https://github.com/SNUCSE-CTA/SymBi)

   *Seunghwan Min, Sung Gwan Park, Kunsoo Park, Dora Giammarresi, Giuseppe F. Italiano, Wook-Shin Han.* 

1. **Space-Efficient Subgraph Search Over Streaming Graph With Timing Order Constraint.**  IEEE Trans. Knowl. Data Eng. 34(9): 4453-4467 (2022) [[paper]](https://ieeexplore.ieee.org/document/9248627)

   *Youhuan Li, Lei Zou, M. Tamer Özsu, Dongyan Zhao.* 

1. **Time Constrained Continuous Subgraph Search Over Streaming Graphs.** ICDE 2019: 1082-1093 [[paper]](https://ieeexplore.ieee.org/document/8731446) [[code]](https://github.com/pkumod/timingsubg)

   *Youhuan Li, Lei Zou, M. Tamer Özsu, Dongyan Zhao.*

1. **TurboFlux: A Fast Continuous Subgraph Matching System for Streaming Graph Data.** SIGMOD Conference 2018: 411-426 [[paper]](https://dl.acm.org/doi/10.1145/3183713.3196917)

   *Kyoungmin Kim, In Seo, Wook-Shin Han, Jeong-Hoon Lee, Sungpack Hong, Hassan Chafi, Hyungyu Shin, Geonhwa Jeong.*

1. **General dynamic Yannakakis: conjunctive queries with theta joins under updates.** VLDB J. 29(2-3): 619-653 (2020) [[paper]](https://link.springer.com/article/10.1007/s00778-019-00590-9)

   *Muhammad Idris, Martín Ugarte, Stijn Vansummeren, Hannes Voigt, Wolfgang Lehner.*

1. **The Dynamic Yannakakis Algorithm: Compact and Efficient Query Processing Under Updates.** SIGMOD Conference 2017: 1259-1274 [[paper]](https://dl.acm.org/doi/10.1145/3035918.3064027)

   *Muhammad Idris, Martín Ugarte, Stijn Vansummeren.*

1. **Graphflow: An active graph database.** SIGMOD Conference 2017: 1695-1698 [[paper]](https://dl.acm.org/doi/10.1145/3035918.3056445)

   *Chathura Kankanamge, Siddhartha Sahu, Amine Mhedhbi, Jeremy Chen, Semih Salihoglu.* 
   
1. **A Selectivity based approach to Continuous Pattern Detection in Streaming Graphs.** EDBT 2015: 157-168 [[paper]](https://openproceedings.org/2015/conf/edbt/paper-307.pdf) [[slides]](https://sutanay.github.io/publications/StreamWorks_BlueHat.pdf)

   *Sutanay Choudhury, Lawrence B. Holder, George Chin Jr., Khushbu Agarwal, John Feo.*

1. **Incremental graph pattern matching.** ACM Trans. Database Syst. 38(3): 18 (2013) [[paper]](https://dl.acm.org/doi/10.1145/2489791)

   *Wenfei Fan, Xin Wang, Yinghui Wu.*

1. **Incremental graph pattern matching.** SIGMOD Conference 2011: 925-936 [[paper]](https://dl.acm.org/doi/10.1145/1989323.1989420)

   *Wenfei Fan, Jianzhong Li, Jizhou Luo, Zijing Tan, Xin Wang, Yinghui Wu.* 

### [Regular Path Query](#content) 

1. **MWP: Multi-Window Parallel Evaluation of Regular Path Queries on Streaming Graphs.** Proc. ACM Manag. Data 2(1): 5:1-5:26 (2024) [[paper]](https://dl.acm.org/doi/10.1145/3639260)

   *Siyuan Zhang, Zhenying He, Yinan Jing, Kai Zhang, X. Sean Wang.* 

1. **LM-SRPQ: Efficiently Answering Regular Path Query in Streaming Graphs.** Proc. VLDB Endow. 17(5): 1047-1059 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p1047-zou.pdf) [[code]](https://github.com/StreamingTriangle/LM-SRPQ)

   *Xiangyang Gou, Xinyi Ye, Lei Zou, Jeffrey Xu Yu.* 

1. **Evaluating complex queries on streaming graphs.** ICDE 2022: 272-285 [[paper]](https://ieeexplore.ieee.org/document/9835463) [[code]](https://github.com/dsg-uwaterloo/s-graffito) [[slides]](https://cs.uwaterloo.ca/~apacaci/papers/icde_longtalk_20220423.pdf) [[video]](https://www.youtube.com/watch?v=r1t1xZXrvzM)

   *Anil Pacaci, Angela Bonifati, M. Tamer Özsu.* 

1. **Regular Path Query Evaluation on Streaming Graphs.** SIGMOD Conference 2020: 1415-1430 [[paper]](https://dl.acm.org/doi/10.1145/3318464.3389733) [[slides]](https://cs.uwaterloo.ca/~apacaci/papers/sigmod2020.pdf) [[video]](https://dl.acm.org/doi/10.1145/3318464.3389733#sec-supp)

   *Anil Pacaci, Angela Bonifati, M. Tamer Özsu.* 

## [Approximation Algorithms](#content)

### [Triangle Count](#content) 

1. **GREAT: Generalized Reservoir Sampling based Triangle Counting Estimation over Streaming Graphs.** Proc. VLDB Endow. 18(7): 2031-2043 (2025) [[paper]](https://www.vldb.org/pvldb/vol18/p2031-wu.pdf) [[code]](https://github.com/sinhong-cheuk/GREAT)

   *Siyue Wu, Dingming Wu, Sinhong Cheuk, Tsz Nam Chan, Kezhong Lu.*

1. **DTC: Real-Time and Accurate Distributed Triangle Counting in Fully Dynamic Graph Streams.** SRDS 2024: 198-209 [[paper]](https://doi.org/10.1109/SRDS64841.2024.00028) [[code]](https://github.com/anonymous4cs/Real-Time-and-Accurate-Distributed-Triangle-Counting-in-Fully-Dynamic-Graph-Streams)

   *Wei Xuan, Yan Liang, Huawei Cao, Ning Lin, Xiaochun Ye, Dongrui Fan.*

1. **Fast and Accurate Triangle Counting in Graph Streams Using Predictions.** ICDM 2024: 31-40 [[paper]](https://doi.org/10.1109/ICDM59182.2024.00010) [[code]](https://github.com/VandinLab/Tonic)

   *Cristian Boldrin, Fabio Vandin.*

1. **Compact Estimator for Streaming Triangle Counting.** IEEE Trans. Knowl. Data Eng. 36(8): 3712-3724 (2024) [[paper]](https://doi.org/10.1109/TKDE.2024.3371228)

   *Jiqing Gu, Chao Song, Haipeng Dai, Li Lu, Ming Liu.*

1. **A distributed streaming framework for edge-cloud triangle counting in graph streams.** Knowl. Based Syst. 278: 110878 (2023) [[paper]](https://doi.org/10.1016/j.knosys.2023.110878) [[code]](https://github.com/yangx0517/TbEC/tree/master)

   *Xu Yang, Chao Song, Jiqing Gu, Ke Li, Hongwei Li.* 

1. **Sliding window-based approximate triangle counting with bounded memory usage.** VLDB J. 32(5): 1087-1110 (2023) [[paper]](https://doi.org/10.1007/s00778-023-00783-3) [[code]](https://github.com/StreamingTriangleCounting/TriangleCounting)

   *Xiangyang Gou, Lei Zou.* 

1. **Sliding Window-based Approximate Triangle Counting over Streaming Graphs with Duplicate Edges.** SIGMOD Conference 2021: 645-657 [[paper]](https://dl.acm.org/doi/10.1145/3448016.3452800) [[code]](https://github.com/XiangyangGou-pku/TriangleCounting)

   *Xiangyang Gou, Lei Zou.* 

1. **Distributed Triangle Approximately Counting Algorithms in Simple Graph Stream.** ACM Trans. Knowl. Discov. Data 16(4): 79:1-79:43 (2022) [[paper]](https://doi.org/10.1145/3494562) [[code]](https://github.com/yangx0517/Distributed-triangle-approximately-counting-algorithms-in-simple-graph-stream)

   *Xu Yang, Chao Song, Mengdi Yu, Jiqing Gu, Ming Liu.* 

1. **Distributed Triangle Counting Algorithms in Simple Graph Stream.** ICPADS 2019: 294-301 [[paper]](https://doi.org/10.1109/ICPADS47876.2019.00049)

   *Mengdi Yu, Chao Song, Jiqing Gu, Ming Liu.* 

1. **CoCoS: Fast and Accurate Distributed Triangle Counting in Graph Streams.** ACM Trans. Knowl. Discov. Data 15(3): 38:1-38:30 (2021) [[paper]](https://doi.org/10.1145/3441487) [[code]](https://github.com/kijungs/cocos)

   *Kijung Shin, Euiwoong Lee, Jinoh Oh, Mohammad Hammoud, Christos Faloutsos.* 

1. **Tri-Fly: Distributed Estimation of Global and Local Triangle Counts in Graph Streams.** PAKDD (3) 2018: 651-663 [[paper]](https://doi.org/10.1007/978-3-319-93040-4_51) [[code]](https://github.com/kijungs/trifly)

   *Kijung Shin, Mohammad Hammoud, Euiwoong Lee, Jinoh Oh, Christos Faloutsos.* 

1. **Fast, Accurate and Provable Triangle Counting in Fully Dynamic Graph Streams.** ACM Trans. Knowl. Discov. Data 14(2): 12:1-12:39 (2020) [[paper]](https://doi.org/10.1145/3375392) [[code]](https://github.com/kijungs/thinkd)

   *Kijung Shin, Sejoon Oh, Jisu Kim, Bryan Hooi, Christos Faloutsos.* 

1. **Think Before You Discard: Accurate Triangle Counting in Graph Streams with Deletions.** ECML/PKDD (2) 2018: 141-157 [[paper]](https://doi.org/10.1007/978-3-030-10928-8_9) [[code]](https://github.com/kijungs/thinkd)

   *Kijung Shin, Jisu Kim, Bryan Hooi, Christos Faloutsos.* 

1. **Temporal locality-aware sampling for accurate triangle counting in real graph streams.** VLDB J. 29(6): 1501-1525 (2020) [[paper]](https://doi.org/10.1007/s00778-020-00624-7) [[code]](https://github.com/kijungs/waiting_room)

   *Dongjin Lee, Kijung Shin, Christos Faloutsos.* 

1. **WRS: Waiting Room Sampling for Accurate Triangle Counting in Real Graph Streams.** . ICDM 2017: 1087-1092 [[paper]](https://doi.org/10.1109/ICDM.2017.143) [[code]](https://github.com/kijungs/waiting_room)

   *Kijung Shin.* 

1. **REPT: A Streaming Algorithm of Approximating Global and Local Triangle Counts in Parallel.** ICDE 2019: 758-769 [[paper]](https://doi.org/10.1109/ICDE.2019.00073)

   *Pinghui Wang, Peng Jia, Yiyan Qi, Yu Sun, Jing Tao, Xiaohong Guan* 

1. **FURL: Fixed-memory and uncertainty reducing local triangle counting for multigraph streams.** Data Min. Knowl. Discov. 33(5): 1225-1253 (2019) [[paper]](https://doi.org/10.1007/s10618-019-00630-6) [[Code]](https://datalab.snu.ac.kr/furl/furl-v1.0.zip)

   *Minsoo Jung, Yongsub Lim, Sunmin Lee, U Kang.* 

1. **Memory-Efficient and Accurate Sampling for Counting Local Triangles in Graph Streams: From Simple to Multigraphs.** ACM Trans. Knowl. Discov. Data 12(1): 4:1-4:28 (2018) [[paper]](https://dl.acm.org/doi/10.1145/3022186) [[Code]](http://datalab.snu.ac.kr/paper/mascot/mascot_v1.0.zip)

   *Yongsub Lim, Minsoo Jung, U Kang.* 

1. **MASCOT: Memory-efficient and Accurate Sampling for Counting Local Triangles in Graph Streams.** KDD 2015: 685-694 [[paper]](https://dl.acm.org/doi/10.1145/2783258.2783285) [[Code]](http://datalab.snu.ac.kr/paper/mascot/mascot_v1.0.zip)

   *Yongsub Lim, U Kang.* 

1. **Approximately Counting Triangles in Large Graph Streams Including Edge Duplicates with a Fixed Memory Usage.** Proc. VLDB Endow. 11(2): 162-175 (2017) [[paper]](https://www.vldb.org/pvldb/vol11/p162-wang.pdf)

   *Pinghui Wang, Yiyan Qi, Yu Sun, Xiangliang Zhang, Jing Tao, Xiaohong Guan.* 

1. **TRIÈST: Counting Local and Global Triangles in Fully Dynamic Streams with Fixed Memory Size.** ACM Trans. Knowl. Discov. Data 11(4): 43:1-43:50 (2017) [[paper]](https://dl.acm.org/doi/10.1145/3059194) [[code]](https://github.com/aepasto/triest)

   *Lorenzo De Stefani, Alessandro Epasto, Matteo Riondato, Eli Upfal.* 

1. **TRIÈST: Counting Local and Global Triangles in Fully-Dynamic Streams with Fixed Memory Size.** KDD 2016: 825-834 [[paper]](https://dl.acm.org/doi/10.1145/2939672.2939771) [[code]](https://github.com/aepasto/triest)

   *Lorenzo De Stefani, Alessandro Epasto, Matteo Riondato, Eli Upfal.* 
 
### [Butterfly Count](#content)

1. **FABLE: Approximate Butterfly Counting in Bipartite Graph Stream with Duplicate Edges.** CIKM 2024: 2158-2167 [[paper]](https://dl.acm.org/doi/10.1145/3627673.3679812)

   *Guozhang Sun, Yuhai Zhao, Yuan Li.*
   
1. **Counting Butterflies in Fully Dynamic Bipartite Graph Streams.** ICDE 2024: 2917-2930 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00226)

   *Serafeim Papadias, Zoi Kaoudi, Varun Pandey, Jorge-Arnulfo Quiané-Ruiz, Volker Markl.* 

1. **Approximately Counting Butterflies in Large Bipartite Graph Streams.** IEEE Trans. Knowl. Data Eng. 34(12): 5621-5635 (2022) [[paper]](https://ieeexplore.ieee.org/document/9366975)

   *Rundong Li, Pinghui Wang, Peng Jia, Xiangliang Zhang, Junzhou Zhao, Jing Tao, Ye Yuan, Xiaohong Guan.* 

1. **sGrapp: Butterfly Approximation in Streaming Graphs.** ACM Trans. Knowl. Discov. Data 16(4): 76:1-76:43 (2022) [[paper]](https://dl.acm.org/doi/10.1145/3495011) [[code]](https://github.com/dsg-uwaterloo/s-graffito/blob/master/files/sGrapp_artifacts.zip)

   *Aida Sheshbolouki, M. Tamer Özsu.* 

1. **FLEET: Butterfly Estimation from a Bipartite Graph Stream.** CIKM 2019: 1201-1210 [[paper]](https://dl.acm.org/doi/10.1145/3357384.3357983) [[code]](https://github.com/beginner1010/fleet)

   *Seyed-Vahid Sanei-Mehri, Yu Zhang, Ahmet Erdem Sariyüce, Srikanta Tirthapura.* 
