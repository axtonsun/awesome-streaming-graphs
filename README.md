# awesome-streaming-graphs
[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

Must-read papers on streaming graph

## [Content](#content)

<table>
<tr><td colspan="2"><a href="#keynote">1. Keynote</a></td></tr> 
<tr><td colspan="2"><a href="#survey-papers">2. Survey</a></td></tr> 
<tr><td colspan="2"><a href="#system">3. System</a></td></tr> 
<tr><td colspan="2"><a href="#graph-stream-summarization">4. Graph Stream Summarization</a></td></tr> 
<tr><td colspan="2"><a href="#exact-algorithms">5. Exact Algorithms</a></td></tr>
<tr>
    <td>&ensp;<a href="#subgraph-matching">5.1 Subgraph Matching</a></td>
    <td>&ensp;<a href="#regular-path-query">5.2 Regular Path Query</a></td>
</tr>
<tr><td colspan="2"><a href="#approximation-algorithms">6. Approximation Algorithms</a></td></tr>
<tr>
    <td>&ensp;<a href="#triangle-count">6.1 Triangle Count</a></td>
    <td>&ensp;<a href="#butterfly-count">6.2 Butterfly Count</a></td>
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
1. **图数据流的模型、算法和系统[J].** 大数据, 2018, 4(4): 44-55. [[paper]](http://www.infocomm-journal.com/bdr/CN/10.11959/j.issn.2096-0271.2018039)
   
   *李友焕, 邹磊.*  
   
1. **Graph stream algorithms: a survey.** SIGMOD Rec. 43(1): 9-20 (2014) [[paper]](https://doi.org/10.1145/2627692.2627694)
   
   *Andrew McGregor.* 
   
## [System](#content)
1. **RisGraph: A Real-Time Streaming System for Evolving Graphs to Support Sub-millisecond Per-update Analysis at Millions Ops/s.** SIGMOD Conference 2021: 513-527 [[paper]](https://dl.acm.org/doi/10.1145/3448016.3457263)

   *Guanyu Feng, Zixuan Ma, Daixuan Li, Shengqi Chen, Xiaowei Zhu, Wentao Han, Wenguang Chen*
   
1. **GraphOne: A Data Store for Real-time Analytics on Evolving Graphs.** FAST 2019: 249-263 [[paper]](https://www.usenix.org/conference/fast19/presentation/kumar) [[slides]](https://www.usenix.org/sites/default/files/conference/protected-files/fast19_slides_kumar.pdf) [[video]](https://www.youtube.com/watch?v=Pqps3bz1LE0) 

   *Pradeep Kumar, H. Howie Huang.* 

## [Graph Stream Summarization](#content)

1. **Auxo: A Scalable and Efficient Graph Stream Summarization Structure.** Proc. VLDB Endow. 16(6): 1386-1398 (2023) [[paper]](https://www.vldb.org/pvldb/vol16/p1386-chen.pdf)

   *Zhiguo Jiang, Hanhua Chen, Hai Jin.* 

1. **Horae: A Graph Stream Summarization Structure for Efficient Temporal Range Query.** ICDE 2022: 2792-2804 [[paper]](https://doi.org/10.1109/ICDE53745.2022.00254)

   *Ming Chen, Renxiang Zhou, Hanhua Chen, Jiang Xiao, Hai Jin, Bo Li.* 
   
1. **Scube: Efficient Summarization for Skewed Graph Streams.** ICDCS 2022: 100-110 [[paper]](https://doi.org/10.1109/ICDCS54860.2022.00019)

   *Ming Chen, Renxiang Zhou, Hanhua Chen, Hai Jin.* 

1. **Graph Stream Sketch: Summarizing Graph Streams With High Speed and Accuracy.** IEEE Trans. Knowl. Data Eng. 35(6): 5901-5914 (2023) [[paper]](https://doi.org/10.1109/TKDE.2022.3174570)

   *Xiangyang Gou, Lei Zou, Chenxingyu Zhao, Tong Yang.* 

1. **Fast and Accurate Graph Stream Summarization.** ICDE 2019: 1118-1129 [[paper]](https://doi.org/10.1109/ICDE.2019.00103)

   *Xiangyang Gou, Lei Zou, Chenxingyu Zhao, Tong Yang.* 

1. **Incremental Lossless Graph Summarization.**  KDD 2020: 317-327 [[paper]](https://dl.acm.org/doi/10.1145/3394486.3403074) [[slides]](https://www.slideshare.net/ssuserd6bbc0/incremental-lossless-graph-summarization-kdd-2020) [[video]](https://youtu.be/FHVx642GoaI) 

   *Jihoon Ko, Yunbum Kook, Kijung Shin.* 

1. **Graph Stream Summarization: From Big Bang to Big Crunch.** SIGMOD Conference 2016: 1481-1496 [[paper]](https://dl.acm.org/doi/10.1145/2882903.2915223) [[slides]](https://prezi.com/wj5kw9wbmr8o/tcm/)

   *Nan Tang, Qing Chen, Prasenjit Mitra.* 

## [Exact Algorithms](#content) 

### [Subgraph Matching](#content) 

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

1. **LM-SRPQ: Efficiently Answering Regular Path Query in Streaming Graphs.** Proc. VLDB Endow. 17(5): 1047-1059 [[paper]](https://www.vldb.org/pvldb/vol17/p1047-zou.pdf) [[code]](https://github.com/StreamingTriangle/LM-SRPQ)

   *Xiangyang Gou, Xinyi Ye, Lei Zou, Jeffrey Xu Yu.* 

1. **Evaluating complex queries on streaming graphs.** ICDE 2022: 272-285 [[paper]](https://ieeexplore.ieee.org/document/9835463) [[code]](https://github.com/dsg-uwaterloo/s-graffito) [[slides]](https://cs.uwaterloo.ca/~apacaci/papers/icde_longtalk_20220423.pdf) [[video]](https://www.youtube.com/watch?v=r1t1xZXrvzM)

   *Anil Pacaci, Angela Bonifati, M. Tamer Özsu.* 

1. **Regular Path Query Evaluation on Streaming Graphs.** SIGMOD Conference 2020: 1415-1430 [[paper]](https://dl.acm.org/doi/10.1145/3318464.3389733) [[slides]](https://cs.uwaterloo.ca/~apacaci/papers/sigmod2020.pdf) [[video]](https://dl.acm.org/doi/10.1145/3318464.3389733#sec-supp)

   *Anil Pacaci, Angela Bonifati, M. Tamer Özsu.* 

## [Approximation Algorithms](#content)

### [Triangle Count](#content) 

1. **Sliding Window-based Approximate Triangle Counting over Streaming Graphs with Duplicate Edges.** SIGMOD Conference 2021: 645-657 [[paper]](https://dl.acm.org/doi/10.1145/3448016.3452800)

   *Xiangyang Gou, Lei Zou.* 
   
1. **Memory-Efficient and Accurate Sampling for Counting Local Triangles in Graph Streams: From Simple to Multigraphs.** ACM Trans. Knowl. Discov. Data 12(1): 4:1-4:28 (2018) [[paper]](https://dl.acm.org/doi/10.1145/3022186)

   *Yongsub Lim, Minsoo Jung, U Kang.* 
   
1. **TRIÈST: Counting Local and Global Triangles in Fully-Dynamic Streams with Fixed Memory Size..** KDD 2016: 825-834 [[paper]](https://dl.acm.org/doi/10.1145/2939672.2939771)

   *Lorenzo De Stefani, Alessandro Epasto, Matteo Riondato, Eli Upfal.* 
 
### [Butterfly Count](#content)

1. **Counting Butterflies in Fully Dynamic Bipartite Graph Streams.** ICDE 2024 [[paper]](https://arxiv.org/abs/2312.03435)

   *Serafeim Papadias, Zoi Kaoudi, Varun Pandey, Jorge-Arnulfo Quiané-Ruiz, Volker Markl.* 

1. **Approximately Counting Butterflies in Large Bipartite Graph Streams.** IEEE Trans. Knowl. Data Eng. 34(12): 5621-5635 (2022) [[paper]](https://ieeexplore.ieee.org/document/9366975)

   *Rundong Li, Pinghui Wang, Peng Jia, Xiangliang Zhang, Junzhou Zhao, Jing Tao, Ye Yuan, Xiaohong Guan.* 


1. **sGrapp: Butterfly Approximation in Streaming Graphs.** ACM Trans. Knowl. Discov. Data 16(4): 76:1-76:43 (2022) [[paper]](https://dl.acm.org/doi/10.1145/3495011) [[code]](https://github.com/dsg-uwaterloo/s-graffito/blob/master/files/sGrapp_artifacts.zip)

   *Aida Sheshbolouki, M. Tamer Özsu.* 

1. **FLEET: Butterfly Estimation from a Bipartite Graph Stream.** CIKM 2019: 1201-1210 [[paper]](https://dl.acm.org/doi/10.1145/3357384.3357983) [[code]](https://github.com/beginner1010/fleet)

   *Seyed-Vahid Sanei-Mehri, Yu Zhang, Ahmet Erdem Sariyüce, Srikanta Tirthapura.* 
