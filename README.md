# awesome-streaming-graphs
[![Awesome](https://awesome.re/badge.svg)](https://github.com/axtonsun/awesome-streaming-graphs)
![](https://img.shields.io/github/last-commit/axtonsun/awesome-streaming-graphs?color=green) 
![](https://img.shields.io/github/stars/axtonsun/awesome-streaming-graphs)
![](https://img.shields.io/badge/PRs-Welcome-red)

Must-read papers on streaming graphs

## [Content](#content)

<table>
<tr><td colspan="2"><a href="#keynotes">1. Keynotes</a></td></tr>
<tr><td colspan="2"><a href="#surveys">2. Surveys</a></td></tr>
<tr><td colspan="2"><a href="#systems">3. Systems</a></td></tr>
<tr><td colspan="2"><a href="#streaming-graph-partitioning">4. Streaming Graph Partitioning</a></td></tr>
<tr><td colspan="2"><a href="#summarization--sampling">5. Summarization & Sampling</a></td></tr>
<tr><td>&ensp;<a href="#graph-stream-summarization">5.1 Graph Stream Summarization</a></td><td>&ensp;<a href="#graph-sampling">5.2 Graph Sampling</a></td></tr>
<tr><td colspan="2"><a href="#continuous-queries">6. Continuous Queries</a></td></tr>
<tr><td>&ensp;<a href="#subgraph-matching">6.1 Subgraph Matching</a></td><td>&ensp;<a href="#regular-path-query">6.2 Regular Path Query</a></td></tr>
<tr><td>&ensp;<a href="#reachability">6.3 Reachability</a></td><td>&ensp;<a href="#shortest-path">6.4 Shortest Path</a></td></tr>
<tr><td>&ensp;<a href="#connectivity">6.5 Connectivity</a></td></tr>
<tr><td colspan="2"><a href="#subgraph-counting--mining">7. Subgraph Counting & Mining</a></td></tr>
<tr><td>&ensp;<a href="#triangle-count">7.1 Triangle Count</a></td><td>&ensp;<a href="#butterfly-count">7.2 Butterfly Count</a></td></tr>
<tr><td>&ensp;<a href="#subgraph-counting">7.3 Subgraph Counting</a></td><td>&ensp;<a href="#frequent-subgraph-mining">7.4 Frequent Subgraph Mining</a></td></tr>
<tr><td>&ensp;<a href="#cycle-clique--biclique">7.5 Cycle, Clique & Biclique</a></td></tr>
<tr><td colspan="2"><a href="#cohesive-subgraphs--communities">8. Cohesive Subgraphs & Communities</a></td></tr>
<tr><td>&ensp;<a href="#core--tip-decomposition">8.1 Core & Tip Decomposition</a></td><td>&ensp;<a href="#dense-subgraph">8.2 Dense Subgraph</a></td></tr>
<tr><td>&ensp;<a href="#community-detection">8.3 Community Detection</a></td><td>&ensp;<a href="#community-search">8.4 Community Search</a></td></tr>
<tr><td>&ensp;<a href="#graph-clustering">8.5 Graph Clustering</a></td></tr>
<tr><td colspan="2"><a href="#graph-analytics">9. Graph Analytics</a></td></tr>
<tr><td colspan="2"><a href="#anomaly--event-detection">10. Anomaly & Event Detection</a></td></tr>
<tr><td>&ensp;<a href="#anomaly-detection">10.1 Anomaly Detection</a></td><td>&ensp;<a href="#burst--event-detection">10.2 Burst & Event Detection</a></td></tr>
<tr><td>&ensp;<a href="#concept-drift">10.3 Concept Drift</a></td></tr>
<tr><td colspan="2"><a href="#learning-on-streaming-graphs">11. Learning on Streaming Graphs</a></td></tr>
<tr><td>&ensp;<a href="#representation-learning">11.1 Representation Learning</a></td><td>&ensp;<a href="#node--graph-classification">11.2 Node & Graph Classification</a></td></tr>
<tr><td>&ensp;<a href="#link-prediction--recommendation">11.3 Link Prediction & Recommendation</a></td><td>&ensp;<a href="#generation--forecasting">11.4 Generation & Forecasting</a></td></tr>
</table>

## [Tags](#content)

Each paper entry ends with tags:

- **Result**
  - `Exact`: Returns the exact answer to the problem as defined, including randomized methods that do so with high probability (e.g., connectivity sketches).
  - `Approx`: Returns an estimate or approximation (sketching, sampling, heuristics, or learned estimators).
  - *Note:* Neural-network detectors in Section 10.1 and papers in Section 11 carry no result tag.
- **Data model** *(tags from the two groups below can be combined)*
  - **Updates**
    - `Insert-only`: Edges (or graphs) only arrive, with no deletions.
    - `Fully dynamic`: Edges can be both inserted and deleted; edge-weight increases and decreases (as in dynamic road networks) also count.
  - **Arrival**
    - `Sliding window`: Only edges within a recent time or count window are valid while older edges expire; expiration is not deletion.
    - `Snapshots`: The input is a sequence of graph snapshots.
    - *Default:* Without either tag, updates arrive one by one as an edge stream.

> **Edge cases:** A paper may carry both `Insert-only` and `Fully dynamic` when it presents a separate method for each model. A `Snapshots` paper may omit the update tag when it does not specify whether edges are deleted between snapshots.

## [Keynotes](#content)

1. **Streaming Graph Processing and Analytics.** [[slides]](https://cs.uwaterloo.ca/~tozsu/presentations/streaming_graph.pdf) [[DEBS'20 video]](https://www.youtube.com/watch?v=wKJvm_O-Gyc) [[PKUMOD'20 video]](https://www.bilibili.com/video/BV1u54y1S7wj)

   *M. Tamer Özsu.*

1. **Graph Processing: A Panoramic View and Some Open Problems.** [[slides]](https://cs.uwaterloo.ca/~tozsu/presentations/VLDB19-keynote.pdf) [[VLDB'19 video]](https://www.youtube.com/watch?v=IjChB1tkIrA) [[PKUMOD'20 video]](https://www.bilibili.com/video/BV1QK4y147yz)

   *M. Tamer Özsu.*

1. **An Introduction to Graph Analytics Platform - Very Short Version.** [[slides]](https://cs.uwaterloo.ca/~tozsu/presentations/Graph-analytics-shortest.pdf)

   *M. Tamer Özsu.*

## [Surveys](#content)

1. **Practice of Streaming Processing of Dynamic Graphs: Concepts, Models, and Systems.** IEEE Trans. Parallel Distributed Syst. 34(6): 1860-1876 (2023) [[paper]](https://doi.org/10.1109/tpds.2021.3131677)

   *Maciej Besta, Marc Fischer, Vasiliki Kalavri, Michael Kapralov, Torsten Hoefler.*

1. **图数据流的模型、算法和系统[J].** 大数据, 2018, 4(4): 44-55. [[paper]](https://doi.org/10.11959/j.issn.2096-0271.2018039)

   *李友焕, 邹磊.*

1. **Graph stream algorithms: a survey.** SIGMOD Rec. 43(1): 9-20 (2014) [[paper]](https://doi.org/10.1145/2627692.2627694)

   *Andrew McGregor.*

## [Systems](#content)

1. **A Comprehensive Survey on Dynamic Graph Processing: Storage and Analytics.** IEEE Trans. Knowl. Data Eng. 38(5): 2488-2507 (2026) [[paper]](https://doi.org/10.1109/tkde.2026.3667713) `Survey`

   *Yuan Zhang, Huawei Cao, Yue Shen, Sibo Li, Yang Feng, Chunxiang Wang, Xuejun An, Xiaochun Ye.*

1. **CEGraph: Cache-Efficient Management for Streaming Graph Processing.** IEEE Trans. Comput. Aided Des. Integr. Circuits Syst. 45(1): 108-119 (2026) [[paper]](https://doi.org/10.1109/tcad.2025.3575362) `Fully dynamic`

   *Fubing Mao, Zihan Xie, Longyu Nie, Yu Zhang, Haikun Liu, Xiaofei Liao, Hai Jin, Wei Zhang, Yapu Guo, Jingkang Liu.*

1. **DCSR: A Fast Data Structure with Leaf-Oriented Locks for Streaming Graph Processing.** EDBT 2026: 359-371 [[paper]](https://doi.org/10.48786/edbt.2026.29) `Fully dynamic`

   *Yue Shen, Jie Zhang, Huawei Cao, Yuan Zhang, Xuejun An.*

1. **SVSIG: Incremental Streaming Graph Processing with Source Vertex Suppression.** ICS 2026: 539-550 [[paper]](https://doi.org/10.1145/3797905.3807850) `Fully dynamic`

   *Jianqiang Huang, Xiao Yan, Dapeng Fu, Haodong Bian, Tengfei Cao, Zhixiong Li.*

1. **WSGraph: A Framework for Tackling Redundant and Irregular Data Access in Streaming Graph Processing.** ACM Trans. Archit. Code Optim. 23(2): 54:1-54:25 (2026) [[paper]](https://doi.org/10.1145/3803023) `Fully dynamic`

   *Xuanyi Li, Chen Li, Zhengyi Dai, Xiaowen Chen, Jianzhuang Lu, Yang Guo.*

1. **CISGraph: A Contribution-Driven Accelerator for Pairwise Streaming Graph Analytics.** DATE 2025: 1-7 [[paper]](https://doi.org/10.23919/date64628.2025.10993039) `Fully dynamic`

   *Songyu Feng, Mo Zou, Tian Zhi, Zidong Du.*

1. **Efficient Graph Data Access for Out-of-Memory GPU Streaming Graph Processing.** Proc. VLDB Endow. 18(11): 3854-3867 (2025) [[paper]](https://www.vldb.org/pvldb/vol18/p3854-wang.pdf) [[code]](https://github.com/Yongze-zzz/C-GpuStreamGraph) `Fully dynamic`

   *Qiange Wang, Yongze Yan, Hongshi Tan, Cheng Chen, Cheng Zhao, Jiaming Tian, Jiaxin Jiang, Xiaoliang Cong, Yanfeng Zhang, Ge Yu, Weng-Fai Wong, Bingsheng He.*

1. **AeonG: An Efficient Built-in Temporal Support in Graph Databases.** Proc. VLDB Endow. 17(6): 1515-1527 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p1515-lu.pdf) [[code]](https://github.com/hououou/AeonG) `Fully dynamic`

   *Jiamin Hou, Zhanhao Zhao, Zhouyu Wang, Wei Lu, Guodong Jin, Dong Wen, Xiaoyong Du.*

1. **LSGraph: A Locality-centric High-performance Streaming Graph Engine.** EuroSys 2024: 33-49 [[paper]](https://doi.org/10.1145/3627703.3650076) `Fully dynamic`

   *Hao Qi, Yiyang Wu, Ligang He, Yu Zhang, Kang Luo, Minzhi Cai, Hai Jin, Zhan Zhang, Jin Zhao.*

1. **PDG: A Prefetcher for Dynamic Graph Updating.** IEEE Trans. Comput. Aided Des. Integr. Circuits Syst. 43(4): 1246-1259 (2024) [[paper]](https://doi.org/10.1109/tcad.2023.3335880) `Insert-only`

   *Xinmiao Zhang, Cheng Liu, Jiacheng Ni, Yuanqing Cheng, Lei Zhang, Huawei Li, Xiaowei Li.*

1. **PMGraph: Accelerating Concurrent Graph Queries over Streaming Graphs.** ACM Trans. Archit. Code Optim. 21(4): 88:1-88:25 (2024) [[paper]](https://doi.org/10.1145/3689337) `Fully dynamic`

   *Fubing Mao, Xu Liu, Yu Zhang, Haikun Liu, Xiaofei Liao, Hai Jin, Wei Zhang, Jian Zhou, Yufei Wu, Longyu Nie, Yapu Guo, Zihan Jiang, Jingkang Liu.*

1. **TARIS: Scalable Incremental Processing of Time-Respecting Algorithms on Streaming Graphs.** IEEE Trans. Parallel Distributed Syst. 35(12): 2527-2544 (2024) [[paper]](https://doi.org/10.1109/tpds.2024.3471574) `Fully dynamic`

   *Ruchi Bhoot, Suved Sanjay Ghanmode, Yogesh Simmhan.*

1. **ACGraph: Accelerating Streaming Graph Processing via Dependence Hierarchy.** DAC 2023: 1-6 [[paper]](https://doi.org/10.1109/dac56929.2023.10247904) `Fully dynamic`

   *Zihan Jiang, Fubing Mao, Yapu Guo, Xu Liu, Haikun Liu, Xiaofei Liao, Hai Jin, Wei Zhang.*

1. **GeaFlow: A Graph Extended and Accelerated Dataflow System.** Proc. ACM Manag. Data 1(2): 191:1-191:27 (2023) [[paper]](https://doi.org/10.1145/3589771) `Fully dynamic`

   *Zhenxuan Pan, Tao Wu, Qingwen Zhao, Qiang Zhou, Zhiwei Peng, Jiefeng Li, Qi Zhang, Guanyu Feng, Xiaowei Zhu.*

1. **GraphFly: Efficient Asynchronous Streaming Graphs Processing via Dependency-Flow.** SC 2022: 45:1-45:14 [[paper]](https://dl.acm.org/doi/10.5555/3571885.3571944) `Fully dynamic`

   *Dan Chen, Chuangyi Gui, Yi Zhang, Hai Jin, Long Zheng, Yu Huang, Xiaofei Liao.*

1. **Optimizing Differentially-Maintained Recursive Queries on Dynamic Graphs.** Proc. VLDB Endow. 15(11): 3186-3198 (2022) [[paper]](https://www.vldb.org/pvldb/vol15/p3186-ammar.pdf) [[code]](https://github.com/khaledammar/optimized-DC) `Fully dynamic`

   *Khaled Ammar, Siddhartha Sahu, Semih Salihoglu, M. Tamer Özsu.*

1. **TDGraph: a topology-driven accelerator for high-performance streaming graph processing.** ISCA 2022: 116-129 [[paper]](https://doi.org/10.1145/3470496.3527409) `Fully dynamic`

   *Jin Zhao, Yun Yang, Yu Zhang, Xiaofei Liao, Lin Gu, Ligang He, Bingsheng He, Hai Jin, Haikun Liu, Xinyu Jiang, Hui Yu.*

1. **Automating Incremental Graph Processing with Flexible Memoization.** Proc. VLDB Endow. 14(9): 1613-1625 (2021) [[paper]](https://www.vldb.org/pvldb/vol14/p1613-gong.pdf) `Fully dynamic`

   *Shufeng Gong, Chao Tian, Qiang Yin, Wenyuan Yu, Yanfeng Zhang, Liang Geng, Song Yu, Ge Yu, Jingren Zhou.*

1. **Controlling Memory Footprint of Stateful Streaming Graph Processing.** USENIX ATC 2021: 269-283 [[paper]](https://www.usenix.org/system/files/atc21-vaziri.pdf) [[slides]](https://www.usenix.org/system/files/atc21_slides_vaziri.pdf) [[video]](https://www.youtube.com/watch?v=Jg_LRUEbMkc) `Fully dynamic`

   *Pourya Vaziri, Keval Vora.*

1. **DZiG: sparsity-aware incremental processing of streaming graphs.** EuroSys 2021: 83-98 [[paper]](https://doi.org/10.1145/3447786.3456230) `Fully dynamic`

   *Mugilan Mariappan, Joanna Che, Keval Vora.*

1. **Exploiting Buffered Updates for Fast Streaming Graph Analysis.** IEEE Trans. Computers 70(2): 255-269 (2021) [[paper]](https://doi.org/10.1109/tc.2020.2987571) `Fully dynamic`

   *Feng Sheng, Qiang Cao, Jie Yao.*

1. **RisGraph: A Real-Time Streaming System for Evolving Graphs to Support Sub-millisecond Per-update Analysis at Millions Ops/s.** SIGMOD Conference 2021: 513-527 [[paper]](https://doi.org/10.1145/3448016.3457263) `Fully dynamic`

   *Guanyu Feng, Zixuan Ma, Daixuan Li, Shengqi Chen, Xiaowei Zhu, Wentao Han, Wenguang Chen.*

1. **Terrace: A Hierarchical Graph Container for Skewed Dynamic Graphs.** SIGMOD Conference 2021: 1372-1385 [[paper]](https://doi.org/10.1145/3448016.3457313) `Fully dynamic`

   *Prashant Pandey, Brian Wheatman, Helen Xu, Aydin Buluc.*

1. **Tripoline: generalized incremental graph processing via graph triangle inequality.** EuroSys 2021: 17-32 [[paper]](https://doi.org/10.1145/3447786.3456226) `Insert-only`

   *Xiaolin Jiang, Chengshuo Xu, Xizhe Yin, Zhijia Zhao, Rajiv Gupta.*

1. **Dolha - an efficient and exact data structure for streaming graphs.** World Wide Web 23(2): 873-903 (2020) [[paper]](https://doi.org/10.1007/s11280-019-00762-1) `Fully dynamic` `Sliding window`

   *Fan Zhang, Lei Zou, Li Zeng, Xiangyang Gou.*

1. **GraphBolt: Dependency-Driven Synchronous Processing of Streaming Graphs.** EuroSys 2019: 25:1-25:16 [[paper]](https://doi.org/10.1145/3302424.3303974) `Fully dynamic`

   *Mugilan Mariappan, Keval Vora.*

1. **GraphOne: A Data Store for Real-time Analytics on Evolving Graphs.** FAST 2019: 249-263 [[paper]](https://www.usenix.org/conference/fast19/presentation/kumar) [[slides]](https://www.usenix.org/sites/default/files/conference/protected-files/fast19_slides_kumar.pdf) [[video]](https://www.youtube.com/watch?v=Pqps3bz1LE0) `Fully dynamic`

   *Pradeep Kumar, H. Howie Huang.*

1. **KickStarter: Fast and Accurate Computations on Streaming Graphs via Trimmed Approximations.** ASPLOS 2017: 237-251 [[paper]](https://doi.org/10.1145/3037697.3037748) `Fully dynamic`

   *Keval Vora, Rajiv Gupta, Guoqing Xu.*

## [Streaming Graph Partitioning](#content)

1. **FREIGHT: Fast Streaming Hypergraph Partitioning.** Algorithmica 87(3): 405-428 (2025) [[paper]](https://doi.org/10.1007/s00453-024-01291-8)

   *Kamal Eyubov, Marcelo Fonseca Faraj, Christian Schulz.*

1. **Triparts: Scalable Streaming Graph Partitioning to Enhance Community Structure.** Proc. VLDB Endow. 18(9): 2992-3006 (2025) [[paper]](https://www.vldb.org/pvldb/vol18/p2992-simmhan.pdf) [[code]](https://github.com/dream-lab/triparts)

   *Ruchi Bhoot, Tuhin Khare, Manoj Agarwal, Siddharth Jaiswal, Yogesh Simmhan.*

1. **CUTTANA: Scalable Graph Partitioning for Faster Distributed Graph Databases and Analytics.** Proc. VLDB Endow. 18(1): 14-27 (2024) [[paper]](https://www.vldb.org/pvldb/vol18/p14-hajidehi.pdf) [[code]](https://github.com/cuttana)

   *Milad Rezaei Hajidehi, Sraavan Sridhar, Margo I. Seltzer.*

1. **Play like a Vertex: A Stackelberg Game Approach for Streaming Graph Partitioning.** Proc. ACM Manag. Data 2(3): 162 (2024) [[paper]](https://doi.org/10.1145/3654965)

   *Zezhong Ding, Yongan Xiang, Shangyou Wang, Xike Xie, S. Kevin Zhou.*

1. **A Mixed-State Streaming Edge Partitioning based on Combinatorial Design.** ICDM 2023: 868-877 [[paper]](https://doi.org/10.1109/ICDM58522.2023.00096)

   *Zhenyu Zhang, Wenwen Qu, Weixi Zhang, Junlin Shang, Xiaoling Wang.*

1. **Attribute-driven streaming edge partitioning with reconciliations for distributed graph neural network training.** Neural Networks 165: 987-998 (2023) [[paper]](https://doi.org/10.1016/j.neunet.2023.06.026)

   *Zongshen Mu, Siliang Tang, Yueting Zhuang, Dianhai Yu.*

1. **Lightweight Streaming Graph Partitioning by Fully Utilizing Knowledge from Local View.** ICDCS 2023: 614-625 [[paper]](https://doi.org/10.1109/ICDCS57875.2023.00079)

   *Zhigang Wang, Zichao Yang, Ning Wang, Yujie Du, Jie Nie, Zhiqiang Wei, Yu Gu, Ge Yu.*

1. **Out-of-Core Edge Partitioning at Linear Run-Time.** ICDE 2022: 2629-2642 [[paper]](https://doi.org/10.1109/ICDE53745.2022.00242) [[code]](https://github.com/mayerrn/two_phase_streaming)

   *Ruben Mayer, Kamil Orujzade, Hans-Arno Jacobsen.*

1. **Recursive Multi-Section on the Fly: Shared-Memory Streaming Algorithms for Hierarchical Graph Partitioning and Process Mapping.** CLUSTER 2022: 473-483 [[paper]](https://doi.org/10.1109/cluster51413.2022.00057)

   *Marcelo Fonseca Faraj, Christian Schulz.*

1. **Experimental Analysis of Streaming Algorithms for Graph Partitioning.** SIGMOD Conference 2019: 1375-1392 [[paper]](https://doi.org/10.1145/3299869.3300076) [[code]](https://github.com/anilpacaci/streaming-graph-partitioning) `Benchmark`

   *Anil Pacaci, M. Tamer Özsu.*

1. **Quasi-Streaming Graph Partitioning: A Game Theoretical Approach.** IEEE Trans. Parallel Distributed Syst. 30(7): 1643-1656 (2019) [[paper]](https://doi.org/10.1109/TPDS.2018.2890515)

   *Qiang-Sheng Hua, Yangyang Li, Dongxiao Yu, Hai Jin.*

1. **Streaming Graph Partitioning: An Experimental Study.** Proc. VLDB Endow. 11(11): 1590-1603 (2018) [[paper]](https://www.vldb.org/pvldb/vol11/p1590-abbas.pdf) `Benchmark`

   *Zainab Abbas, Vasiliki Kalavri, Paris Carbone, Vladimir Vlassov.*

1. **Modeling, analysis, and experimental comparison of streaming graph-partitioning policies.** J. Parallel Distributed Comput. 108: 106-121 (2017) [[paper]](https://doi.org/10.1016/j.jpdc.2016.02.003) `Benchmark`

   *Yong Guo, Sungpack Hong, Hassan Chafi, Alexandru Iosup, Dick Epema.*

1. **HDRF: Stream-Based Partitioning for Power-Law Graphs.** CIKM 2015: 243-252 [[paper]](https://doi.org/10.1145/2806416.2806424)

   *Fabio Petroni, Leonardo Querzoni, Khuzaima Daudjee, Shahin Kamali, Giorgio Iacoboni.*

1. **Distributed Power-law Graph Computing: Theoretical and Empirical Analysis.** NIPS 2014: 1673-1681 [[paper]](https://papers.nips.cc/paper_files/paper/2014/hash/3a794b71830091b1e8048312eb649c88-Abstract.html)

   *Cong Xie, Ling Yan, Wu-Jun Li, Zhihua Zhang.*

1. **FENNEL: streaming graph partitioning for massive scale graphs.** WSDM 2014: 333-342 [[paper]](https://doi.org/10.1145/2556195.2556213)

   *Charalampos E. Tsourakakis, Christos Gkantsidis, Bozidar Radunovic, Milan Vojnovic.*

1. **GraphBuilder: scalable graph ETL framework.** GRADES 2013: 4 [[paper]](https://doi.org/10.1145/2484425.2484429)

   *Nilesh Jain, Guangdeng Liao, Theodore L. Willke.*

1. **PowerGraph: Distributed Graph-Parallel Computation on Natural Graphs.** OSDI 2012: 17-30 [[paper]](https://www.usenix.org/conference/osdi12/technical-sessions/presentation/gonzalez)

   *Joseph E. Gonzalez, Yucheng Low, Haijie Gu, Danny Bickson, Carlos Guestrin.*

1. **Streaming graph partitioning for large distributed graphs.** KDD 2012: 1222-1230 [[paper]](https://doi.org/10.1145/2339530.2339722)

   *Isabelle Stanton, Gabriel Kliot.*

## [Summarization & Sampling](#content)

### [Graph Stream Summarization](#content)

1. **Crane: An Accurate and Scalable Neural Sketch for Graph Stream Summarization.** Proc. ACM Manag. Data 4(6): 330 (2026) [[paper]](https://arxiv.org/abs/2602.15360) `Approx` `Insert-only`

   *Boyan Wang, Zhuochen Fan, Dayu Wang, Fangcheng Fu, Zeyu Luan, Lei Zou, Qing Li, Tong Yang.*

1. **GeminiSketch: An Accurate and Efficient Sketch for Summarizing Temporal Graph Streams with Rolling-Out Elimination.** ICDE 2026: 30-43 [[paper]](https://doi.org/10.1109/icde65706.2026.00010) `Approx` `Sliding window`

   *Xuyang Jing, Chenhao Zhang, Zheng Yan, Qingze Jiang, Witold Pedrycz, Mingjun Wang, Cong Wang.*

1. **GRIT: An Accurate and Efficient Graph Stream Summarization for Temporal Query.** CIKM 2025: 888-897 [[paper]](https://doi.org/10.1145/3746252.3761105) `Approx` `Insert-only`

   *Jingxian Hu, Guozhang Sun, Xin Wang, Yuhai Zhao, Yuan Li, Xingwei Wang.*

1. **HIGGS: HIerarchy-Guided Graph Stream Summarization.** ICDE 2025: 1470-1482 [[paper]](https://doi.org/10.1109/ICDE65448.2025.00114) `Approx` `Fully dynamic`

   *Xuan Zhao, Xike Xie, Christian S. Jensen.*

1. **HourglassSketch: An Efficient and Scalable Framework for Graph Stream Summarization.** ICDE 2025: 114-127 [[paper]](https://doi.org/10.1109/ICDE65448.2025.00016) [[code]](https://github.com/HourglassSketch/HourglassSketch-code) `Approx` `Insert-only`

   *Jiarui Guo, Boxuan Chen, Kaicheng Yang, Tong Yang, Zirui Liu, Qiuheng Yin, Sha Wang, Yuhan Wu, Xiaolin Wang, Bin Cui, Tao Li, Xi Peng, Renhai Chen, Gong Zhang.*

1. **LSketch: A label-enabled graph stream sketch toward time-sensitive queries.** Inf. Sci. 691: 121624 (2025) [[paper]](https://doi.org/10.1016/j.ins.2024.121624) `Approx` `Sliding window`

   *Yiling Zeng, Chuanfeng Jian, Chunyao Song, Tingjian Ge, Yuhan Li, Yuqing Zhou.*

1. **Sliding-ITeM: An Adaptive-Size Graph Stream Summarization Structure Based on Sliding Windows.** Data Sci. Eng. 10(3): 428-454 (2025) [[paper]](https://doi.org/10.1007/s41019-024-00279-2) `Approx` `Sliding window`

   *Yacheng Wang, Hanhua Chen, Hao Chen, Hai Jin.*

1. **Toward accurate weight-based measurement and periodic edge measurement in graph stream.** World Wide Web 28(6): 63 (2025) [[paper]](https://doi.org/10.1007/s11280-025-01378-4) `Approx` `Insert-only`

   *Zhuo Li, YuXuan Zhao, Jindian Liu, Yu Zhang, Kaihua Liu.*

1. **Conditional heavy hitter monitoring and application of heterogeneous graph streams based on sketches.** Inf. Process. Manag. 61(4): 103762 (2024) [[paper]](https://doi.org/10.1016/j.ipm.2024.103762) [[code]](https://github.com/Crystal-1224/HeavyHitter) `Approx` `Insert-only`

   *Chuanfeng Jian, Yiling Zeng, Chunyao Song, Ying Zhang.*

1. **Learning to Sketch: A Neural Approach to Item Frequency Estimation in Streaming Data.** IEEE Trans. Pattern Anal. Mach. Intell. 46(11): 7136-7153 (2024) [[paper]](https://doi.org/10.1109/TPAMI.2024.3388589) [[code]](https://github.com/FFY0/MetaSketch_TPAMI) `Approx` `Insert-only`

   *Yukun Cao, Yuan Feng, Hairu Wang, Xike Xie, S. Kevin Zhou.*

1. **Mayfly: a Neural Data Structure for Graph Stream Summarization.** ICLR 2024 [[paper]](https://openreview.net/pdf?id=n7Sr8SW4bn) [[code]](https://openreview.net/attachment?id=n7Sr8SW4bn&name=supplementary_material) `Approx` `Insert-only`

   *Yuan Feng, Yukun Cao, Hairu Wang, Xike Xie, S. Kevin Zhou.*

1. **SIM: A fast real-time graph stream summarization with improved memory efficiency and accuracy.** Comput. Networks 248: 110502 (2024) [[paper]](https://doi.org/10.1016/j.comnet.2024.110502) `Approx` `Insert-only`

   *Zhuo Li, Shuaijun Liu, Jindian Liu, Yu Zhang, Teng Liang, Kaihua Liu.*

1. **Auxo: A Scalable and Efficient Graph Stream Summarization Structure.** Proc. VLDB Endow. 16(6): 1386-1398 (2023) [[paper]](https://www.vldb.org/pvldb/vol16/p1386-chen.pdf) [[code]](https://github.com/CGCL-codes/Auxo) `Approx` `Insert-only`

   *Zhiguo Jiang, Hanhua Chen, Hai Jin.*

1. **Graph Stream Sketch: Summarizing Graph Streams With High Speed and Accuracy.** IEEE Trans. Knowl. Data Eng. 35(6): 5901-5914 (2023) [[paper]](https://doi.org/10.1109/TKDE.2022.3174570) `Approx` `Fully dynamic`

   *Xiangyang Gou, Lei Zou, Chenxingyu Zhao, Tong Yang.*

1. **Learning-Based Dichotomy Graph Sketch for Summarizing Graph Streams with High Accuracy.** KSEM 2023: 47-59 [[paper]](https://doi.org/10.1007/978-3-031-40286-9_5) `Approx` `Insert-only`

   *Ding Li, Wenzhong Li, Yizhou Chen, Xu Zhong, Mingkai Lin, Sanglu Lu.*

1. **Persistent graph stream summarization for real-time graph analytics.** World Wide Web 26(5): 2647-2667 (2023) [[paper]](https://doi.org/10.1007/s11280-023-01165-z) `Approx` `Insert-only`

   *Yan Jia, Zhaoquan Gu, Zhihao Jiang, Cuiyun Gao, Jianye Yang.*

1. **A parameter-free approach to lossless summarization of fully dynamic graphs.** Inf. Sci. 589: 376-394 (2022) [[paper]](https://doi.org/10.1016/j.ins.2021.12.116) `Exact` `Fully dynamic`

   *Ziyi Ma, Yuling Liu, Zhibang Yang, Jianye Yang, Kenli Li.*

1. **Dynamic Graph Summarization: Optimal and Scalable.** IEEE BigData 2022: 545-554 [[paper]](https://doi.org/10.1109/bigdata55660.2022.10020422) `Exact` `Fully dynamic`

   *Mahdi Hajiabadi, Venkatesh Srinivasan, Alex Thomo.*

1. **Horae: A Graph Stream Summarization Structure for Efficient Temporal Range Query.** ICDE 2022: 2792-2804 [[paper]](https://doi.org/10.1109/ICDE53745.2022.00254) `Approx` `Insert-only`

   *Ming Chen, Renxiang Zhou, Hanhua Chen, Jiang Xiao, Hai Jin, Bo Li.*

1. **Scube: Efficient Summarization for Skewed Graph Streams.** ICDCS 2022: 100-110 [[paper]](https://doi.org/10.1109/ICDCS54860.2022.00019) `Approx` `Insert-only`

   *Ming Chen, Renxiang Zhou, Hanhua Chen, Hai Jin.*

1. **A Parameter-Free Approach for Lossless Streaming Graph Summarization.** DASFAA (1) 2021: 385-393 [[paper]](https://doi.org/10.1007/978-3-030-73194-6_26) `Exact` `Insert-only`

   *Ziyi Ma, Jianye Yang, Kenli Li, Yuling Liu, Xu Zhou, Yikun Hu.*

1. **DMatrix: Toward fast and accurate queries in graph stream.** Comput. Networks 198: 108403 (2021) [[paper]](https://doi.org/10.1016/j.comnet.2021.108403) [[code]](https://github.com/houchangsheng/DMatrix) `Approx` `Insert-only`

   *Changsheng Hou, Bingnan Hou, Tongqing Zhou, Zhiping Cai.*

1. **GS4: Graph stream summarization based on both the structure and semantics.** J. Supercomput. 77(3): 2713-2733 (2021) [[paper]](https://doi.org/10.1007/s11227-020-03290-2) `Approx` `Sliding window`

   *Nosratali Ashrafi-Payaman, Mohammad Reza Kangavari, Saeid Hosseini, Amir Mohammad Fander.*

1. **Learning-Based Dynamic Graph Stream Sketch.** PAKDD 2021: 383-394 [[paper]](https://doi.org/10.1007/978-3-030-75762-5_31) `Approx` `Insert-only`

   *Ding Li, Wenzhong Li, Yizhou Chen, Mingkai Lin, Sanglu Lu.*

1. **Incremental Lossless Graph Summarization.** KDD 2020: 317-327 [[paper]](https://doi.org/10.1145/3394486.3403074) [[slides]](https://www.slideshare.net/ssuserd6bbc0/incremental-lossless-graph-summarization-kdd-2020) [[video]](https://youtu.be/FHVx642GoaI) `Exact` `Fully dynamic`

   *Jihoon Ko, Yunbum Kook, Kijung Shin.*

1. **Fast and Accurate Graph Stream Summarization.** ICDE 2019: 1118-1129 [[paper]](https://doi.org/10.1109/ICDE.2019.00103) [[code]](https://github.com/Puppy95/Graph-Stream-Sketch) `Approx` `Insert-only`

   *Xiangyang Gou, Lei Zou, Chenxingyu Zhao, Tong Yang.*

1. **Labeled graph sketches: Keeping up with real-time graph streams.** Inf. Sci. 503: 469-492 (2019) [[paper]](https://doi.org/10.1016/j.ins.2019.07.019) `Approx` `Fully dynamic` `Sliding window`

   *Chunyao Song, Tingjian Ge, Yao Ge, Haowen Zhang, Xiaojie Yuan.*

1. **SBG-sketch: a self-balanced sketch for labeled-graph stream summarization.** SSDBM 2018: 3:1-3:12 [[paper]](https://doi.org/10.1145/3221269.3223030) `Approx` `Insert-only`

   *Mohamed S. Hassan, Bruno Ribeiro, Walid G. Aref.*

1. **Graph Stream Summarization: From Big Bang to Big Crunch.** SIGMOD Conference 2016: 1481-1496 [[paper]](https://doi.org/10.1145/2882903.2915223) [[slides]](https://prezi.com/wj5kw9wbmr8o/tcm/) `Approx` `Fully dynamic`

   *Nan Tang, Qing Chen, Prasenjit Mitra.*

1. **Query-friendly compression of graph streams.** ASONAM 2016: 130-137 [[paper]](https://doi.org/10.1109/asonam.2016.7752224) `Approx` `Insert-only`

   *Arijit Khan, Charu C. Aggarwal.*

1. **gSketch: On Query Estimation in Graph Streams.** Proc. VLDB Endow. 5(3): 193-204 (2011) [[paper]](https://www.vldb.org/pvldb/vol5/p193_peixiangzhao_vldb2012.pdf) `Approx` `Insert-only`

   *Peixiang Zhao, Charu C. Aggarwal, Min Wang.*

### [Graph Sampling](#content)

1. **Computing Graph Descriptors on Edge Streams.** ACM Trans. Knowl. Discov. Data 17(8): 112:1-112:25 (2023) [[paper]](https://doi.org/10.1145/3591468) `Approx` `Insert-only`

   *Zohair Raza Hassan, Sarwan Ali, Imdadullah Khan, Mudassir Shabbir, Waseem Abbas.*

1. **Adaptive Shrinkage Estimation for Streaming Graphs.** NeurIPS 2020 [[paper]](https://papers.nips.cc/paper_files/paper/2020/hash/780261c4b9a55cd803080619d0cc3e11-Abstract.html) `Approx` `Insert-only`

   *Nesreen K. Ahmed, Nick Duffield.*

1. **Cluster-preserving sampling from fully-dynamic streaming graphs.** Inf. Sci. 482: 279-300 (2019) [[paper]](https://doi.org/10.1016/j.ins.2019.01.011) `Approx` `Fully dynamic`

   *Jianpeng Zhang, Kaijie Zhu, Yulong Pei, George Fletcher, Mykola Pechenizkiy.*

1. **ComPAS: Community Preserving Sampling for Streaming Graphs.** AAMAS 2018: 184-192 [[paper]](https://doi.org/10.65109/wjfu4736) `Approx` `Insert-only`

   *Sandipan Sikdar, Tanmoy Chakraborty, Soumya Sarkar, Niloy Ganguly, Animesh Mukherjee.*

1. **On sampling from massive graph streams.** Proc. VLDB Endow. 10(11): 1430-1441 (2017) [[paper]](https://www.vldb.org/pvldb/vol10/p1430-ahmed.pdf) `Approx` `Insert-only`

   *Nesreen K. Ahmed, Nick Duffield, Theodore L. Willke, Ryan A. Rossi.*

1. **Graph sample and hold: a framework for big-graph analytics.** KDD 2014: 1446-1455 [[paper]](https://doi.org/10.1145/2623330.2623757) `Approx` `Insert-only`

   *Nesreen K. Ahmed, Nick Duffield, Jennifer Neville, Ramana Kompella.*

1. **Network Sampling: From Static to Streaming Graphs.** ACM Trans. Knowl. Discov. Data 8(2): 7:1-7:56 (2014) [[paper]](https://doi.org/10.1145/2601438) `Approx` `Insert-only`

   *Nesreen K. Ahmed, Jennifer Neville, Ramana Kompella.*

## [Continuous Queries](#content)

### [Subgraph Matching](#content)

1. **An Extensive Experimental Study of Indexes in Continuous Subgraph Matching.** Proc. ACM Manag. Data 4(1): 9:1-9:26 (2026) [[paper]](https://doi.org/10.1145/3786623) `Exact` `Fully dynamic` `Benchmark`

   *Xiangyang Gou, Lei Zou, Jeffrey Xu Yu, Wenjie Zhang.*

1. **Efficient Multi-Query Optimization for Continuous Subgraph Matching Over Streaming Graphs.** IEEE Trans. Knowl. Data Eng. 38(11): 7445-7460 (2026) [[paper]](https://doi.org/10.1109/tkde.2026.3721816) [[code]](https://github.com/ShermonMa/MQAM) `Exact` `Fully dynamic`

   *Ziyi Ma, Xinming Ma, Jianye Yang, Liang Yang, Lihua Yin, Xuemin Lin.*

1. **Privacy-Preserving Analytics on Outsourced Streaming Graphs: The Case of Pattern Detection.** IEEE Trans. Knowl. Data Eng. 38(5): 3037-3051 (2026) [[paper]](https://doi.org/10.1109/tkde.2026.3673371) `Exact` `Fully dynamic` `Sliding window`

   *Songlei Wang, Yifeng Zheng, Xiaohua Jia.*

1. **Continuous Subgraph Matching via Cost-Model-based Dynamic Vertex Dominance Embeddings.** Proc. ACM Manag. Data 3(6): 309:1-309:27 (2025) [[paper]](https://doi.org/10.1145/3769774) `Exact` `Fully dynamic`

   *Yutong Ye, Xiang Lian, Nan Zhang, Mingsong Chen.*

1. **CSM-TopK: Continuous Subgraph Matching with TopK Density Constraints.** ICDE 2024: 3084-3097 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00239) [[code]](https://github.com/chuchugao2/CSMTopk) `Exact` `Fully dynamic`

   *Chuchu Gao, Youhuan Li, Zhibang Yang, Xu Zhou.*

1. **Efficient Multi-Query Oriented Continuous Subgraph Matching.** ICDE 2024: 3230-3243 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00250) [[code]](https://github.com/paopao-E/MQ-Match) `Exact` `Fully dynamic`

   *Ziyi Ma, Jianye Yang, Xu Zhou, Guoqing Xiao, Jianhua Wang, Liang Yang, Kenli Li, Xuemin Lin.*

1. **GCSM: GPU-Accelerated Continuous Subgraph Matching for Large Graphs.** IPDPS 2024: 1046-1057 [[paper]](https://doi.org/10.1109/ipdps57955.2024.00097) `Exact` `Fully dynamic`

   *Yihua Wei, Peng Jiang.*

1. **GraphGuard: Private Time-Constrained Pattern Detection Over Streaming Graphs in the Cloud.** USENIX Security Symposium 2024 [[paper]](https://www.usenix.org/system/files/usenixsecurity24-wang-songlei.pdf) [[slides]](https://www.usenix.org/system/files/usenixsecurity24_slides-wang-songlei.pdf) [[video]](https://www.youtube.com/watch?v=kftJIwye0ts) `Exact` `Sliding window`

   *Songlei Wang, Yifeng Zheng, Xiaohua Jia.*

1. **In-depth Analysis of Continuous Subgraph Matching in a Common Delta Query Compilation Framework.** Proc. ACM Manag. Data 2(3): 147:1-147:27 (2024) [[paper]](https://doi.org/10.1145/3654950) `Exact` `Fully dynamic` `Benchmark`

   *Yukyoung Lee, Kyoungmin Kim, Wonseok Lee, Wook-Shin Han.*

1. **NewSP: A New Search Process for Continuous Subgraph Matching over Dynamic Graphs.** ICDE 2024: 3324-3337 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00257) `Exact` `Fully dynamic`

   *Ziming Li, Youhuan Li, Xinhuan Chen, Lei Zou, Yang Li, Xiaofeng Yang, Hongbo Jiang.*

1. **TC-Match: Fast Time-constrained Continuous Subgraph Matching.** Proc. VLDB Endow. 17(11): 2791-2804 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p2791-yang.pdf) [[code]](https://github.com/Sh-Fang/TCMatch) `Exact` `Sliding window`

   *Jianye Yang, Sheng Fang, Zhaoquan Gu, Ziyi Ma, Xuemin Lin, Zhihong Tian.*

1. **Time-Constrained Continuous Subgraph Matching Using Temporal Information for Filtering and Backtracking.** ICDE 2024: 3257-3269 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00252) `Exact` `Sliding window`

   *Seunghwan Min, Jihoon Jang, Kunsoo Park, Dora Giammarresi, Giuseppe F. Italiano, Wook-Shin Han.*

1. **A survey of continuous subgraph matching for dynamic graphs.** Knowl. Inf. Syst. 65(3): 945-989 (2023) [[paper]](https://doi.org/10.1007/s10115-022-01753-x) `Survey`

   *Xi Wang, Qianzhen Zhang, Deke Guo, Xiang Zhao.*

1. **Fast Continuous Subgraph Matching over Streaming Graphs via Backtracking Reduction.** Proc. ACM Manag. Data 1(1): 15:1-15:26 (2023) [[paper]](https://doi.org/10.1145/3588695) [[code]](https://github.com/JackChuengQAQ/CaLiG) [[video]](https://dl.acm.org/action/downloadSupplement?doi=10.1145/3588695&file=meeting_09.mp4) `Exact` `Fully dynamic`

   *Rongjian Yang, Zhijie Zhang, Weiguo Zheng, Jeffrey Xu Yu.*

1. **An In-Depth Study of Continuous Subgraph Matching.** Proc. VLDB Endow. 15(7): 1403-1416 (2022) [[paper]](https://www.vldb.org/pvldb/vol15/p1403-sun.pdf) [[code]](https://github.com/RapidsAtHKUST/ContinuousSubgraphMatching) `Exact` `Fully dynamic` `Benchmark`

   *Xibo Sun, Shixuan Sun, Qiong Luo, Bingsheng He.*

1. **Mnemonic: A Parallel Subgraph Matching System for Streaming Graphs.** IPDPS 2022: 313-323 [[paper]](https://doi.org/10.1109/ipdps53621.2022.00038) `Exact` `Fully dynamic` `Sliding window`

   *Bibek Bhattarai, H. Howie Huang.*

1. **RapidFlow: An Efficient Approach to Continuous Subgraph Matching.** Proc. VLDB Endow. 15(11): 2415-2427 (2022) [[paper]](https://www.vldb.org/pvldb/vol15/p2415-sun.pdf) [[code]](https://github.com/shixuansun/RapidFlow) `Exact` `Fully dynamic`

   *Shixuan Sun, Xibo Sun, Bingsheng He, Qiong Luo.*

1. **Space-Efficient Subgraph Search Over Streaming Graph With Timing Order Constraint.** IEEE Trans. Knowl. Data Eng. 34(9): 4453-4467 (2022) [[paper]](https://doi.org/10.1109/tkde.2020.3035902) `Exact` `Sliding window`

   *Youhuan Li, Lei Zou, M. Tamer Özsu, Dongyan Zhao.*

1. **Continuous matching of evolving patterns over dynamic graph data.** World Wide Web 24(3): 721-745 (2021) [[paper]](https://doi.org/10.1007/s11280-020-00860-5) `Exact` `Fully dynamic`

   *Qianzhen Zhang, Deke Guo, Xiang Zhao, Xi Wang.*

1. **Symmetric Continuous Subgraph Matching with Bidirectional Dynamic Programming.** Proc. VLDB Endow. 14(8): 1298-1310 (2021) [[paper]](https://www.vldb.org/pvldb/vol14/p1298-han.pdf) [[code]](https://github.com/SNUCSE-CTA/SymBi) `Exact` `Fully dynamic`

   *Seunghwan Min, Sung Gwan Park, Kunsoo Park, Dora Giammarresi, Giuseppe F. Italiano, Wook-Shin Han.*

1. **Efficient Continuous Multi-Query Processing over Graph Streams.** EDBT 2020: 13-24 [[paper]](https://doi.org/10.5441/002/edbt.2020.03) `Exact` `Insert-only`

   *Lefteris Zervakis, Vinay Setty, Christos Tryfonopoulos, Katja Hose.*

1. **General dynamic Yannakakis: conjunctive queries with theta joins under updates.** VLDB J. 29(2-3): 619-653 (2020) [[paper]](https://doi.org/10.1007/s00778-019-00590-9) `Exact` `Fully dynamic`

   *Muhammad Idris, Martín Ugarte, Stijn Vansummeren, Hannes Voigt, Wolfgang Lehner.*

1. **Time Constrained Continuous Subgraph Search Over Streaming Graphs.** ICDE 2019: 1082-1093 [[paper]](https://doi.org/10.1109/icde.2019.00100) [[code]](https://github.com/pkumod/timingsubg) `Exact` `Sliding window`

   *Youhuan Li, Lei Zou, M. Tamer Özsu, Dongyan Zhao.*

1. **Distributed evaluation of subgraph queries using worst-case optimal low-memory dataflows.** Proc. VLDB Endow. 11(6): 691-704 (2018) [[paper]](https://www.vldb.org/pvldb/vol11/p691-ammar.pdf) `Exact` `Fully dynamic`

   *Khaled Ammar, Frank McSherry, Semih Salihoglu, Manas Joglekar.*

1. **TurboFlux: A Fast Continuous Subgraph Matching System for Streaming Graph Data.** SIGMOD Conference 2018: 411-426 [[paper]](https://doi.org/10.1145/3183713.3196917) `Exact` `Fully dynamic`

   *Kyoungmin Kim, In Seo, Wook-Shin Han, Jeong-Hoon Lee, Sungpack Hong, Hassan Chafi, Hyungyu Shin, Geonhwa Jeong.*

1. **Graphflow: An active graph database.** SIGMOD Conference 2017: 1695-1698 [[paper]](https://doi.org/10.1145/3035918.3056445) `Exact` `Fully dynamic`

   *Chathura Kankanamge, Siddhartha Sahu, Amine Mhedhbi, Jeremy Chen, Semih Salihoglu.*

1. **The Dynamic Yannakakis Algorithm: Compact and Efficient Query Processing Under Updates.** SIGMOD Conference 2017: 1259-1274 [[paper]](https://doi.org/10.1145/3035918.3064027) `Exact` `Fully dynamic`

   *Muhammad Idris, Martín Ugarte, Stijn Vansummeren.*

1. **A Selectivity based approach to Continuous Pattern Detection in Streaming Graphs.** EDBT 2015: 157-168 [[paper]](https://doi.org/10.5441/002/edbt.2015.15) [[slides]](https://sutanay.github.io/publications/StreamWorks_BlueHat.pdf) `Exact` `Sliding window`

   *Sutanay Choudhury, Lawrence B. Holder, George Chin Jr., Khushbu Agarwal, John Feo.*

1. **Event pattern matching over graph streams.** Proc. VLDB Endow. 8(4): 413-424 (2014) [[paper]](https://www.vldb.org/pvldb/vol8/p413-ge.pdf) `Exact` `Sliding window`

   *Chunyao Song, Tingjian Ge, Cindy Chen, Jie Wang.*

1. **Incremental graph pattern matching.** ACM Trans. Database Syst. 38(3): 18 (2013) [[paper]](https://doi.org/10.1145/2489791) `Exact` `Fully dynamic`

   *Wenfei Fan, Xin Wang, Yinghui Wu.*

1. **Incremental graph pattern matching.** SIGMOD Conference 2011: 925-936 [[paper]](https://doi.org/10.1145/1989323.1989420) `Exact` `Fully dynamic`

   *Wenfei Fan, Jianzhong Li, Jizhou Luo, Zijing Tan, Xin Wang, Yinghui Wu.*

1. **Continuous Subgraph Pattern Search over Certain and Uncertain Graph Streams.** IEEE Trans. Knowl. Data Eng. 22(8): 1093-1109 (2010) [[paper]](https://doi.org/10.1109/tkde.2010.67) `Approx` `Fully dynamic`

   *Lei Chen, Changliang Wang.*

1. **Continuous Subgraph Pattern Search over Graph Streams.** ICDE 2009: 393-404 [[paper]](https://doi.org/10.1109/icde.2009.132) `Approx` `Fully dynamic`

   *Changliang Wang, Lei Chen.*

### [Regular Path Query](#content)

1. **DRPQ: Distributed Evaluation of Regular Path Queries On Streaming Graphs.** Proc. ACM Manag. Data 3(6): 317:1-317:27 (2025) [[paper]](https://doi.org/10.1145/3769782) `Exact` `Fully dynamic` `Sliding window`

   *Siyuan Zhang, Kai Zhang, Zhenying He, Yinan Jing, Zhigang Zhao, X. Sean Wang.*

1. **LM-SRPQ: Efficiently Answering Regular Path Query in Streaming Graphs.** Proc. VLDB Endow. 17(5): 1047-1059 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p1047-zou.pdf) [[code]](https://github.com/StreamingTriangle/LM-SRPQ) `Exact` `Sliding window`

   *Xiangyang Gou, Xinyi Ye, Lei Zou, Jeffrey Xu Yu.*

1. **MWP: Multi-Window Parallel Evaluation of Regular Path Queries on Streaming Graphs.** Proc. ACM Manag. Data 2(1): 5:1-5:26 (2024) [[paper]](https://doi.org/10.1145/3639260) `Exact` `Fully dynamic` `Sliding window`

   *Siyuan Zhang, Zhenying He, Yinan Jing, Kai Zhang, X. Sean Wang.*

1. **Seraph: Continuous Queries on Property Graph Streams.** EDBT 2024: 234-247 [[paper]](https://doi.org/10.48786/edbt.2024.21) `Exact` `Sliding window`

   *Christopher Rost, Riccardo Tommasini, Angela Bonifati, Emanuele Della Valle, Erhard Rahm, Keith W. Hare, Stefan Plantikow, Petra Selmer, Hannes Voigt.*

1. **Evaluating complex queries on streaming graphs.** ICDE 2022: 272-285 [[paper]](https://doi.org/10.1109/icde53745.2022.00025) [[code]](https://github.com/dsg-uwaterloo/s-graffito) [[video]](https://www.youtube.com/watch?v=r1t1xZXrvzM) `Exact` `Sliding window`

   *Anil Pacaci, Angela Bonifati, M. Tamer Özsu.*

1. **Regular Path Query Evaluation on Streaming Graphs.** SIGMOD Conference 2020: 1415-1430 [[paper]](https://doi.org/10.1145/3318464.3389733) [[video]](https://dl.acm.org/doi/10.1145/3318464.3389733#sec-supp) `Exact` `Fully dynamic` `Sliding window`

   *Anil Pacaci, Angela Bonifati, M. Tamer Özsu.*

### [Reachability](#content)

1. **Efficient algorithms for reachability and path queries on temporal bipartite graphs.** VLDB J. 33(5): 1399-1426 (2024) [[paper]](https://doi.org/10.1007/s00778-024-00854-z) `Exact` `Insert-only`

   *Kai Wang, Minghao Cai, Xiaoshuang Chen, Xuemin Lin, Wenjie Zhang, Lu Qin, Ying Zhang.*

1. **Reachability Queries on Dynamic Temporal Bipartite Graphs.** SIGSPATIAL/GIS 2023: 97:1-97:11 [[paper]](https://doi.org/10.1145/3589132.3625647) [[code]](https://github.com/Lohan-M/WTB-code) `Exact` `Fully dynamic`

   *Lohan Meunier, Ying Zhao.*

1. **DLCR: efficient indexing for label-constrained reachability queries on large dynamic graphs.** Proc. VLDB Endow. 15(8): 1645-1657 (2022) [[paper]](https://www.vldb.org/pvldb/vol15/p1645-chen.pdf) [[code]](https://github.com/jerchenxin/DP2H-CUHK) `Exact` `Fully dynamic`

   *Xin Chen, You Peng, Sibo Wang, Jeffrey Xu Yu.*

1. **Span-reachability querying in large temporal graphs.** VLDB J. 31(4): 629-647 (2022) [[paper]](https://doi.org/10.1007/s00778-021-00715-z) `Exact` `Insert-only` `Sliding window`

   *Dong Wen, Bohua Yang, Ying Zhang, Lu Qin, Dawei Cheng, Wenjie Zhang.*

1. **Efficient distributed reachability querying of massive temporal graphs.** VLDB J. 28(6): 871-896 (2019) [[paper]](https://doi.org/10.1007/s00778-019-00572-x) `Exact` `Insert-only`

   *Tianming Zhang, Yunjun Gao, Lu Chen, Wei Guo, Shiliang Pu, Baihua Zheng, Christian S. Jensen.*

1. **Reachability and time-based path queries in temporal graphs.** ICDE 2016: 145-156 [[paper]](https://doi.org/10.1109/icde.2016.7498236) `Exact` `Insert-only`

   *Huanhuan Wu, Yuzhen Huang, James Cheng, Jinfeng Li, Yiping Ke.*

1. **Reachability queries on large dynamic graphs: a total order approach.** SIGMOD Conference 2014: 1323-1334 [[paper]](https://doi.org/10.1145/2588555.2612181) `Exact` `Fully dynamic`

   *Andy Diwen Zhu, Wenqing Lin, Sibo Wang, Xiaokui Xiao.*

### [Shortest Path](#content)

1. **DSPC: Efficiently Answering Shortest Path Counting on Dynamic Graphs.** EDBT 2024: 116-128 [[paper]](https://doi.org/10.48786/edbt.2024.11) `Exact` `Fully dynamic`

   *Qingshuai Feng, You Peng, Wenjie Zhang, Xuemin Lin, Ying Zhang.*

1. **Towards Real-Time Counting Shortest Cycles on Dynamic Graphs: A Hub Labeling Approach.** ICDE 2022: 512-524 [[paper]](https://doi.org/10.1109/icde53745.2022.00043) `Exact` `Fully dynamic`

   *Qingshuai Feng, You Peng, Wenjie Zhang, Ying Zhang, Xuemin Lin.*

1. **Distributed Processing of k Shortest Path Queries over Dynamic Road Networks.** SIGMOD Conference 2020: 665-679 [[paper]](https://doi.org/10.1145/3318464.3389735) `Exact` `Fully dynamic`

   *Ziqiang Yu, Xiaohui Yu, Nick Koudas, Yang Liu, Yifan Li, Yueting Chen, Dingyu Yang.*

1. **Efficient shortest path index maintenance on dynamic road networks with theoretical guarantees.** Proc. VLDB Endow. 13(5): 602-615 (2020) [[paper]](https://www.vldb.org/pvldb/vol13/p602-ouyang.pdf) `Exact` `Fully dynamic`

   *Dian Ouyang, Long Yuan, Lu Qin, Lijun Chang, Ying Zhang, Xuemin Lin.*

1. **Distributed shortest path query processing on dynamic road networks.** VLDB J. 26(3): 399-419 (2017) [[paper]](https://doi.org/10.1007/s00778-017-0457-6) `Exact` `Fully dynamic`

   *Dongxiang Zhang, Dingyu Yang, Yuan Wang, Kian-Lee Tan, Jian Cao, Heng Tao Shen.*

1. **Fully Dynamic Shortest-Path Distance Query Acceleration on Massive Networks.** CIKM 2016: 1533-1542 [[paper]](https://doi.org/10.1145/2983323.2983731) `Exact` `Fully dynamic`

   *Takanori Hayashi, Takuya Akiba, Ken-ichi Kawarabayashi.*

1. **Graph Indexing for Shortest-Path Finding over Dynamic Sub-Graphs.** SIGMOD Conference 2016: 1183-1197 [[paper]](https://doi.org/10.1145/2882903.2882933) `Exact` `Fully dynamic`

   *Mohamed S. Hassan, Walid G. Aref, Ahmed M. Aly.*

1. **Dynamic and Historical Shortest-Path Distance Queries on Large Evolving Networks by Pruned Landmark Labeling.** WWW 2014: 237-248 [[paper]](https://doi.org/10.1145/2566486.2568007) `Exact` `Insert-only`

   *Takuya Akiba, Yoichi Iwata, Yuichi Yoshida.*

### [Connectivity](#content)

1. **Maintaining Biconnected Components in Streaming Graphs.** Proc. ACM Manag. Data 4(3): 207:1-207:25 (2026) [[paper]](https://doi.org/10.1145/3802084) `Exact` `Sliding window`

   *Zhao Lu, Dong Wen, Wentao Li, Xuemin Lin, Wenjie Zhang.*

1. **An Experimental Comparison of Tree-data Structures for Connectivity Queries on Fully-dynamic Undirected Graphs.** Proc. ACM Manag. Data 3(1): 10:1-10:26 (2025) [[paper]](https://doi.org/10.1145/3709660) [[code]](https://github.com/qingchen3/Imp_bench_dyn) `Exact` `Fully dynamic` `Benchmark`

   *Qing Chen, Michael H. Böhlen, Sven Helmer.*

1. **Exploring the Landscape of Distributed Graph Sketching.** ALENEX 2025: 133-146 [[paper]](https://doi.org/10.1137/1.9781611978339.11) `Exact` `Fully dynamic`

   *David Tench, Evan T. West, Kenny Zhang, Michael A. Bender, Daniel DeLayo, Martín Farach-Colton, Gilvir Gill, Tyler Seip, Victor Zhang.*

1. **The Case for External Graph Sketching.** ACDA 2025: 115-129 [[paper]](https://doi.org/10.1137/1.9781611979084.9) `Exact` `Fully dynamic`

   *Michael A. Bender, Martín Farach-Colton, Riko Jacob, Hanna Komlós, David Tench, Evan T. West.*

1. **Constant-time Connectivity Querying in Dynamic Graphs.** Proc. ACM Manag. Data 2(6): 230:1-230:23 (2024) [[paper]](https://doi.org/10.1145/3698805) `Exact` `Fully dynamic` `Sliding window`

   *Lantian Xu, Dong Wen, Lu Qin, Rong-Hua Li, Ying Zhang, Xuemin Lin.*

1. **GraphZeppelin: How to Find Connected Components (Even When Graphs Are Dense, Dynamic, and Massive).** ACM Trans. Database Syst. 49(3): 9:1-9:31 (2024) [[paper]](https://doi.org/10.1145/3643846) `Exact` `Fully dynamic`

   *David Tench, Evan T. West, Victor Zhang, Michael A. Bender, Abiyaz Chowdhury, Daniel DeLayo, J. Ahmed Dellas, Martín Farach-Colton, Tyler Seip, Kenny Zhang.*

1. **Incremental Sliding Window Connectivity over Streaming Graphs.** Proc. VLDB Endow. 17(10): 2473-2486 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p2473-zhang.pdf) [[code]](https://github.com/chaozhang-cs/bic) `Exact` `Sliding window`

   *Chao Zhang, Angela Bonifati, M. Tamer Özsu.*

1. **On Querying Historical Connectivity in Temporal Graphs.** Proc. ACM Manag. Data 2(3): 157:1-157:25 (2024) [[paper]](https://doi.org/10.1145/3654960) `Exact` `Insert-only` `Sliding window`

   *Jingyi Song, Dong Wen, Lantian Xu, Lu Qin, Wenjie Zhang, Xuemin Lin.*

1. **Towards Scalable and Practical Batch-Dynamic Connectivity.** Proc. VLDB Endow. 18(3): 889-901 (2024) [[paper]](https://www.vldb.org/pvldb/vol18/p889-dhulipala.pdf) [[code]](https://github.com/ParAlg/DynamicConnectivity) `Exact` `Fully dynamic`

   *Quinten De Man, Laxman Dhulipala, Adam Karczmarz, Jakub Łącki, Julian Shun, Zhongqi Wang.*

1. **Dynamic spanning trees for connectivity queries on fully-dynamic undirected graphs.** Proc. VLDB Endow. 15(11): 3263-3276 (2022) [[paper]](https://www.vldb.org/pvldb/vol15/p3263-chen.pdf) [[code]](https://github.com/qingchen3/D-tree) `Exact` `Fully dynamic`

   *Qing Chen, Oded Lachish, Sven Helmer, Michael H. Böhlen.*

1. **GraphZeppelin: Storage-Friendly Sketching for Connected Components on Dynamic Graph Streams.** SIGMOD Conference 2022: 325-339 [[paper]](https://doi.org/10.1145/3514221.3526146) `Exact` `Fully dynamic`

   *David Tench, Evan T. West, Victor Zhang, Michael A. Bender, Abiyaz Chowdhury, J. Ahmed Dellas, Martín Farach-Colton, Tyler Seip, Kenny Zhang.*

## [Subgraph Counting & Mining](#content)

### [Triangle Count](#content)

1. **高精度滑动窗口模型下的图流三角形近似计数算法[J].** 软件学报, 2025, 36(9): 4349-4372. [[paper]](https://doi.org/10.13328/j.cnki.jos.007256) [[code]](https://github.com/StreamingTriangle/CBS) `Approx` `Sliding window`

   *苟向阳, 邹磊, 于旭.*

1. **GREAT: Generalized Reservoir Sampling based Triangle Counting Estimation over Streaming Graphs.** Proc. VLDB Endow. 18(7): 2031-2043 (2025) [[paper]](https://www.vldb.org/pvldb/vol18/p2031-wu.pdf) [[code]](https://github.com/sinhong-cheuk/GREAT) `Approx` `Insert-only`

   *Siyue Wu, Dingming Wu, Sinhong Cheuk, Tsz Nam Chan, Kezhong Lu.*

1. **A Cloud-Edge Collaborative Framework for Distributed Triangle Counting on Graph Stream.** ICC 2025: 2611-2616 [[paper]](https://doi.org/10.1109/icc52391.2025.11160716) `Approx` `Insert-only`

   *Ruilin Hu, Chao Song, Jie Wu, Li Lu.*

1. **Efficient Approximate Temporal Triangle Counting in Streaming with Predictions.** ECML/PKDD 2025: 244-262 [[paper]](https://doi.org/10.1007/978-3-032-06066-2_15) `Approx` `Insert-only`

   *Giorgio Venturin, Ilie Sarpe, Fabio Vandin.*

1. **DTC: Real-Time and Accurate Distributed Triangle Counting in Fully Dynamic Graph Streams.** SRDS 2024: 198-209 [[paper]](https://doi.org/10.1109/SRDS64841.2024.00028) [[code]](https://github.com/anonymous4cs/Real-Time-and-Accurate-Distributed-Triangle-Counting-in-Fully-Dynamic-Graph-Streams) `Approx` `Fully dynamic`

   *Wei Xuan, Yan Liang, Huawei Cao, Ning Lin, Xiaochun Ye, Dongrui Fan.*

1. **Fast and Accurate Triangle Counting in Graph Streams Using Predictions.** ICDM 2024: 31-40 [[paper]](https://doi.org/10.1109/ICDM59182.2024.00010) [[code]](https://github.com/VandinLab/Tonic) `Approx` `Fully dynamic`

   *Cristian Boldrin, Fabio Vandin.*

1. **Compact Estimator for Streaming Triangle Counting.** IEEE Trans. Knowl. Data Eng. 36(8): 3712-3724 (2024) [[paper]](https://doi.org/10.1109/TKDE.2024.3371228) `Approx` `Insert-only`

   *Jiqing Gu, Chao Song, Haipeng Dai, Li Lu, Ming Liu.*

1. **Efficiently Counting Triangles for Hypergraph Streams by Reservoir-Based Sampling.** IEEE Trans. Knowl. Data Eng. 35(11): 11328-11341 (2023) [[paper]](https://doi.org/10.1109/tkde.2023.3236335) `Approx` `Insert-only`

   *Lingling Zhang, Zhiwei Zhang, Guoren Wang, Ye Yuan, Kangfei Zhao.*

1. **A distributed streaming framework for edge-cloud triangle counting in graph streams.** Knowl. Based Syst. 278: 110878 (2023) [[paper]](https://doi.org/10.1016/j.knosys.2023.110878) [[code]](https://github.com/yangx0517/TbEC/tree/master) `Approx` `Insert-only`

   *Xu Yang, Chao Song, Jiqing Gu, Ke Li, Hongwei Li.*

1. **Sliding window-based approximate triangle counting with bounded memory usage.** VLDB J. 32(5): 1087-1110 (2023) [[paper]](https://doi.org/10.1007/s00778-023-00783-3) [[code]](https://github.com/StreamingTriangleCounting/TriangleCounting) `Approx` `Sliding window`

   *Xiangyang Gou, Lei Zou.*

1. **Distributed Triangle Approximately Counting Algorithms in Simple Graph Stream.** ACM Trans. Knowl. Discov. Data 16(4): 79:1-79:43 (2022) [[paper]](https://doi.org/10.1145/3494562) [[code]](https://github.com/yangx0517/Distributed-triangle-approximately-counting-algorithms-in-simple-graph-stream) `Approx` `Insert-only`

   *Xu Yang, Chao Song, Mengdi Yu, Jiqing Gu, Ming Liu.*

1. **Triangle and Four Cycle Counting with Predictions in Graph Streams.** ICLR 2022 [[paper]](https://openreview.net/forum?id=8in_5gN9I0) `Approx` `Insert-only`

   *Justin Y. Chen, Talya Eden, Piotr Indyk, Honghao Lin, Shyam Narayanan, Ronitt Rubinfeld, Sandeep Silwal, Tal Wagner, David P. Woodruff, Michael Zhang.*

1. **Sliding Window-based Approximate Triangle Counting over Streaming Graphs with Duplicate Edges.** SIGMOD Conference 2021: 645-657 [[paper]](https://doi.org/10.1145/3448016.3452800) [[code]](https://github.com/XiangyangGou-pku/TriangleCounting) `Approx` `Sliding window`

   *Xiangyang Gou, Lei Zou.*

1. **CoCoS: Fast and Accurate Distributed Triangle Counting in Graph Streams.** ACM Trans. Knowl. Discov. Data 15(3): 38:1-38:30 (2021) [[paper]](https://doi.org/10.1145/3441487) [[code]](https://github.com/kijungs/cocos) `Approx` `Insert-only`

   *Kijung Shin, Euiwoong Lee, Jinoh Oh, Mohammad Hammoud, Christos Faloutsos.*

1. **Fast, Accurate and Provable Triangle Counting in Fully Dynamic Graph Streams.** ACM Trans. Knowl. Discov. Data 14(2): 12:1-12:39 (2020) [[paper]](https://doi.org/10.1145/3375392) [[code]](https://github.com/kijungs/thinkd) `Approx` `Fully dynamic`

   *Kijung Shin, Sejoon Oh, Jisu Kim, Bryan Hooi, Christos Faloutsos.*

1. **Temporal locality-aware sampling for accurate triangle counting in real graph streams.** VLDB J. 29(6): 1501-1525 (2020) [[paper]](https://doi.org/10.1007/s00778-020-00624-7) [[code]](https://github.com/kijungs/waiting_room) `Approx` `Fully dynamic`

   *Dongjin Lee, Kijung Shin, Christos Faloutsos.*

1. **Distributed Triangle Counting Algorithms in Simple Graph Stream.** ICPADS 2019: 294-301 [[paper]](https://doi.org/10.1109/ICPADS47876.2019.00049) `Approx` `Insert-only`

   *Mengdi Yu, Chao Song, Jiqing Gu, Ming Liu.*

1. **REPT: A Streaming Algorithm of Approximating Global and Local Triangle Counts in Parallel.** ICDE 2019: 758-769 [[paper]](https://doi.org/10.1109/ICDE.2019.00073) `Approx` `Insert-only`

   *Pinghui Wang, Peng Jia, Yiyan Qi, Yu Sun, Jing Tao, Xiaohong Guan.*

1. **FURL: Fixed-memory and uncertainty reducing local triangle counting for multigraph streams.** Data Min. Knowl. Discov. 33(5): 1225-1253 (2019) [[paper]](https://doi.org/10.1007/s10618-019-00630-6) [[code]](https://datalab.snu.ac.kr/furl/furl-v1.0.zip) `Approx` `Insert-only`

   *Minsoo Jung, Yongsub Lim, Sunmin Lee, U Kang.*

1. **Tri-Fly: Distributed Estimation of Global and Local Triangle Counts in Graph Streams.** PAKDD (3) 2018: 651-663 [[paper]](https://doi.org/10.1007/978-3-319-93040-4_51) [[code]](https://github.com/kijungs/trifly) `Approx` `Insert-only`

   *Kijung Shin, Mohammad Hammoud, Euiwoong Lee, Jinoh Oh, Christos Faloutsos.*

1. **Think Before You Discard: Accurate Triangle Counting in Graph Streams with Deletions.** ECML/PKDD (2) 2018: 141-157 [[paper]](https://doi.org/10.1007/978-3-030-10928-8_9) [[code]](https://github.com/kijungs/thinkd) `Approx` `Fully dynamic`

   *Kijung Shin, Jisu Kim, Bryan Hooi, Christos Faloutsos.*

1. **Memory-Efficient and Accurate Sampling for Counting Local Triangles in Graph Streams: From Simple to Multigraphs.** ACM Trans. Knowl. Discov. Data 12(1): 4:1-4:28 (2018) [[paper]](https://doi.org/10.1145/3022186) [[code]](https://datalab.snu.ac.kr/mascot/) `Approx` `Insert-only`

   *Yongsub Lim, Minsoo Jung, U Kang.*

1. **WRS: Waiting Room Sampling for Accurate Triangle Counting in Real Graph Streams.** ICDM 2017: 1087-1092 [[paper]](https://doi.org/10.1109/ICDM.2017.143) [[code]](https://github.com/kijungs/waiting_room) `Approx` `Insert-only`

   *Kijung Shin.*

1. **Approximately Counting Triangles in Large Graph Streams Including Edge Duplicates with a Fixed Memory Usage.** Proc. VLDB Endow. 11(2): 162-175 (2017) [[paper]](https://www.vldb.org/pvldb/vol11/p162-wang.pdf) `Approx` `Insert-only`

   *Pinghui Wang, Yiyan Qi, Yu Sun, Xiangliang Zhang, Jing Tao, Xiaohong Guan.*

1. **TRIÈST: Counting Local and Global Triangles in Fully Dynamic Streams with Fixed Memory Size.** ACM Trans. Knowl. Discov. Data 11(4): 43:1-43:50 (2017) [[paper]](https://doi.org/10.1145/3059194) [[code]](https://github.com/aepasto/triest) `Approx` `Fully dynamic`

   *Lorenzo De Stefani, Alessandro Epasto, Matteo Riondato, Eli Upfal.*

1. **TRIÈST: Counting Local and Global Triangles in Fully-Dynamic Streams with Fixed Memory Size.** KDD 2016: 825-834 [[paper]](https://doi.org/10.1145/2939672.2939771) [[code]](https://github.com/aepasto/triest) `Approx` `Fully dynamic`

   *Lorenzo De Stefani, Alessandro Epasto, Matteo Riondato, Eli Upfal.*

1. **MASCOT: Memory-efficient and Accurate Sampling for Counting Local Triangles in Graph Streams.** KDD 2015: 685-694 [[paper]](https://doi.org/10.1145/2783258.2783285) [[code]](https://datalab.snu.ac.kr/mascot/) `Approx` `Insert-only`

   *Yongsub Lim, U Kang.*

1. **A Space-Efficient Streaming Algorithm for Estimating Transitivity and Triangle Counts Using the Birthday Paradox.** ACM Trans. Knowl. Discov. Data 9(3): 15:1-15:21 (2015) [[paper]](https://doi.org/10.1145/2700395) `Approx` `Insert-only`

   *Madhav Kumar Jha, Comandur Seshadhri, Ali Pinar.*

1. **A space efficient streaming algorithm for triangle counting using the birthday paradox.** KDD 2013: 589-597 [[paper]](https://doi.org/10.1145/2487575.2487678) `Approx` `Insert-only`

   *Madhav Kumar Jha, Comandur Seshadhri, Ali Pinar.*

1. **Counting and Sampling Triangles from a Graph Stream.** Proc. VLDB Endow. 6(14): 1870-1881 (2013) [[paper]](https://www.vldb.org/pvldb/vol6/p1870-aduri.pdf) `Approx` `Insert-only` `Sliding window`

   *A. Pavan, Kanat Tangwongsan, Srikanta Tirthapura, Kun-Lung Wu.*

1. **Parallel triangle counting in massive streaming graphs.** CIKM 2013: 781-786 [[paper]](https://doi.org/10.1145/2505515.2505741) `Approx` `Insert-only`

   *Kanat Tangwongsan, A. Pavan, Srikanta Tirthapura.*

### [Butterfly Count](#content)

1. **Counting Butterflies over Streaming Bipartite Graphs with Duplicate Edges.** IEEE Trans. Knowl. Data Eng. 38(7): 4200-4212 (2026) [[paper]](https://doi.org/10.1109/tkde.2026.3682749) `Approx` `Insert-only`

   *Lingkai Meng, Long Yuan, Xuemin Lin, Chengjie Li, Kai Wang, Wenjie Zhang.*

1. **FABLE: Approximate Butterfly Counting in Bipartite Graph Stream with Duplicate Edges.** CIKM 2024: 2158-2167 [[paper]](https://doi.org/10.1145/3627673.3679812) `Approx` `Insert-only`

   *Guozhang Sun, Yuhai Zhao, Yuan Li.*

1. **Counting Butterflies in Fully Dynamic Bipartite Graph Streams.** ICDE 2024: 2917-2930 [[paper]](https://doi.org/10.1109/ICDE60146.2024.00226) `Approx` `Fully dynamic`

   *Serafeim Papadias, Zoi Kaoudi, Varun Pandey, Jorge-Arnulfo Quiané-Ruiz, Volker Markl.*

1. **Efficient Temporal Butterfly Counting and Enumeration on Temporal Bipartite Graphs.** Proc. VLDB Endow. 17(4): 657-670 (2023) [[paper]](https://www.vldb.org/pvldb/vol17/p657-gao.pdf) [[code]](https://github.com/ZJU-DAILY/TBFC) `Exact` `Fully dynamic`

   *Xin-Wei Cai, Xiangyu Ke, Kai Wang, Lu Chen, Tianming Zhang, Qing Liu, Yunjun Gao.*

1. **Approximately Counting Butterflies in Large Bipartite Graph Streams.** IEEE Trans. Knowl. Data Eng. 34(12): 5621-5635 (2022) [[paper]](https://doi.org/10.1109/tkde.2021.3062987) `Approx` `Insert-only`

   *Rundong Li, Pinghui Wang, Peng Jia, Xiangliang Zhang, Junzhou Zhao, Jing Tao, Ye Yuan, Xiaohong Guan.*

1. **sGrapp: Butterfly Approximation in Streaming Graphs.** ACM Trans. Knowl. Discov. Data 16(4): 76:1-76:43 (2022) [[paper]](https://doi.org/10.1145/3495011) [[code]](https://github.com/dsg-uwaterloo/s-graffito/blob/master/files/sGrapp_artifacts.zip) `Approx` `Insert-only`

   *Aida Sheshbolouki, M. Tamer Özsu.*

1. **FLEET: Butterfly Estimation from a Bipartite Graph Stream.** CIKM 2019: 1201-1210 [[paper]](https://doi.org/10.1145/3357384.3357983) [[code]](https://github.com/beginner1010/fleet) `Approx` `Insert-only` `Sliding window`

   *Seyed-Vahid Sanei-Mehri, Yu Zhang, Ahmet Erdem Sariyüce, Srikanta Tirthapura.*

### [Subgraph Counting](#content)

1. **An Efficient Streaming Algorithm for Approximating Graphlet Distributions.** Proc. ACM Manag. Data 4(3): 133:1-133:26 (2026) [[paper]](https://doi.org/10.1145/3802010) `Approx` `Insert-only`

   *Marco Bressan, T-H. Hubert Chan, Qipeng Kuang, Mauro Sozio.*

1. **Four-Cycle Counting in Low-Degeneracy Graph Streams.** KDD 2026: 983-994 [[paper]](https://doi.org/10.1145/3770854.3780199) `Approx` `Insert-only`

   *Sebastian Lüderssen, Stefan Neumann, Pan Peng.*

1. **StreamSC: A Learning-Based Framework for Efficient Subgraph Counting in Stream Graphs.** ICDE 2025: 4694-4698 [[paper]](https://doi.org/10.1109/icde65448.2025.00379) `Approx` `Fully dynamic`

   *Zhen Xie, Xiang Zhao.*

1. **Neural subgraph counting on stream graphs via localized updates and monotonic learning.** PLoS ONE 20(10): e0334724 (2025) [[paper]](https://doi.org/10.1371/journal.pone.0334724) `Approx` `Fully dynamic`

   *Zhen Xie, Wenzhe Hou, Feiyang Wu, Hao Xu.*

1. **SGES: A General and Space-efficient Framework for Graphlet Counting in Graph Streams.** CIKM 2024: 2817-2826 [[paper]](https://doi.org/10.1145/3627673.3679739) `Approx` `Insert-only`

   *Chen Yang, Lailong Luo, Yuliang Lu, Chu Huang, Qianzhen Zhang, Guozheng Yang, Deke Guo.*

1. **PSMiner: A Pattern-Aware Accelerator for High-Performance Streaming Graph Pattern Mining.** DAC 2023: 1-6 [[paper]](https://doi.org/10.1109/dac56929.2023.10247902) `Exact` `Insert-only`

   *Hao Qi, Yu Zhang, Ligang He, Kang Luo, Jun Huang, Haoyu Lu, Jin Zhao, Hai Jin.*

1. **Reinforcement Learning Enhanced Weighted Sampling for Accurate Subgraph Counting on Fully Dynamic Graph Streams.** ICDE 2023: 1084-1097 [[paper]](https://doi.org/10.1109/ICDE55515.2023.00088) [[code]](https://github.com/wangkaixin219/WSD) `Approx` `Fully dynamic`

   *Kaixin Wang, Cheng Long, Da Yan, Jie Zhang, H. V. Jagadish.*

1. **Efficient Sampling Algorithms for Approximate Motif Counting in Temporal Graph Streams.** CoRR abs/2211.12101 (2022) [[paper]](https://arxiv.org/abs/2211.12101) `Approx` `Insert-only`

   *Jingjing Wang, Yanhao Wang, Wenjun Jiang, Yuchen Li, Kian-Lee Tan.*

### [Frequent Subgraph Mining](#content)

1. **Discovering Persistent Subgraph Patterns over Streaming Graphs.** DASFAA 2023: 154-171 [[paper]](https://doi.org/10.1007/978-3-031-30675-4_11) `Approx` `Sliding window`

   *Chu Huang, Qianzhen Zhang, Deke Guo, Xiang Zhao.*

1. **Mining Top-k Frequent Patterns over Streaming Graphs.** DASFAA 2023: 199-216 [[paper]](https://doi.org/10.1007/978-3-031-30675-4_14) `Approx` `Insert-only`

   *Xi Wang, Qianzhen Zhang, Deke Guo, Xiang Zhao.*

1. **TipTap: Approximate Mining of Frequent k-Subgraph Patterns in Evolving Graphs.** ACM Trans. Knowl. Discov. Data 15(3): 48:1-48:35 (2021) [[paper]](https://doi.org/10.1145/3442590) `Approx` `Fully dynamic`

   *Muhammad Anis Uddin Nasir, Çiğdem Aslay, Gianmarco De Francisci Morales, Matteo Riondato.*

1. **Mining Persistent Activity in Continually Evolving Networks.** KDD 2020: 934-944 [[paper]](https://doi.org/10.1145/3394486.3403136) [[code]](https://github.com/GemsLab/PENminer) `Exact` `Fully dynamic`

   *Caleb Belth, Xinyi Zheng, Danai Koutra.*

1. **Mining Frequent Patterns in Evolving Graphs.** CIKM 2018: 923-932 [[paper]](https://doi.org/10.1145/3269206.3271772) `Approx` `Fully dynamic`

   *Çiğdem Aslay, Muhammad Anis Uddin Nasir, Gianmarco De Francisci Morales, Aristides Gionis.*

1. **On dense pattern mining in graph streams.** Proc. VLDB Endow. 3(1-2): 975-984 (2010) [[paper]](https://www.vldb.org/pvldb/vol3/R87.pdf) `Approx` `Insert-only`

   *Charu C. Aggarwal, Yao Li, Philip S. Yu, Ruoming Jin.*

### [Cycle, Clique & Biclique](#content)

1. **Maximal η-clique maintenance over uncertain graph streams.** Inf. Sci. 717: 122318 (2025) [[paper]](https://doi.org/10.1016/j.ins.2025.122318) [[code]](https://github.com/paopao-E/Maximal--clique-Maintenance) `Exact` `Fully dynamic`

   *Ziyi Ma, Liqing Wang, Jianye Yang, Xu Zhou, Kenli Li, Cuiyun Gao.*

1. **TopK-BC: Efficient Maintenance of Top k (p,q)-bicliques over Streaming Bipartite Graphs.** ICDE 2025: 3696-3709 [[paper]](https://doi.org/10.1109/icde65448.2025.00276) `Exact` `Sliding window`

   *Xin Deng, Zheng Qin, Peng Peng, Hui Zhou.*

1. **Top-k heavy weight triangles listing on graph stream.** World Wide Web 26(4): 1827-1851 (2023) [[paper]](https://doi.org/10.1007/s11280-022-01117-z) `Approx` `Insert-only`

   *Fan Zhang, Xiangyang Gou, Lei Zou.*

1. **Efficient maintenance for maximal bicliques in bipartite graph streams.** World Wide Web 25(2): 857-877 (2022) [[paper]](https://doi.org/10.1007/s11280-021-00927-x) `Exact` `Fully dynamic`

   *Ziyi Ma, Yuling Liu, Yikun Hu, Jianye Yang, Chubo Liu, Huadong Dai.*

1. **Real-time Constrained Cycle Detection in Large Dynamic Graphs.** Proc. VLDB Endow. 11(12): 1876-1888 (2018) [[paper]](https://www.vldb.org/pvldb/vol11/p1876-qiu.pdf) `Exact` `Sliding window`

   *Xiafei Qiu, Wubin Cen, Zhengping Qian, You Peng, Ying Zhang, Xuemin Lin, Jingren Zhou.*

## [Cohesive Subgraphs & Communities](#content)

### [Core & Tip Decomposition](#content)

1. **Accelerating D-Core Maintenance over Dynamic Directed Graphs.** ICDE 2025: 696-709 [[paper]](https://doi.org/10.1109/icde65448.2025.00058) `Exact` `Fully dynamic`

   *Xuankun Liao, Qing Liu, Jiaxin Jiang, Byron Choi, Bingsheng He, Jianliang Xu.*

1. **Efficient Temporal Edge-Core Maintenance in Streaming Graphs.** Proc. VLDB Endow. 19(4): 726-739 (2025) [[paper]](https://www.vldb.org/pvldb/vol19/p726-tan.pdf) [[code]](https://github.com/naruto110/EdgeCoreMaintenance) `Exact` `Fully dynamic`

   *Tongfeng Weng, Mo Sha, Xu Zhou, Jingjing Lu, Kenli Li, Kian-Lee Tan.*

1. **I/O efficient core maintenance in large graphs.** Expert Syst. Appl. 288: 128234 (2025) [[paper]](https://doi.org/10.1016/j.eswa.2025.128234) `Exact` `Fully dynamic`

   *Jie Dai, Yixiao Liu, Yuan Li, Fazal Wahab, Yuhai Zhao.*

1. **Maintaining Top-t Cores in Dynamic Graphs.** IEEE Trans. Knowl. Data Eng. 36(9): 4766-4780 (2024) [[paper]](https://doi.org/10.1109/tkde.2023.3332638) `Exact` `Fully dynamic`

   *Yikai Zhang, Jeffrey Xu Yu, Ying Zhang, Lu Qin.*

1. **Simplified algorithms for order-based core maintenance.** J. Supercomput. 80(13): 19592-19623 (2024) [[paper]](https://doi.org/10.1007/s11227-024-06190-x) [[code]](https://github.com/Itisben/SimplifiedCoreMaint) `Exact` `Fully dynamic`

   *Bin Guo, Emil Sekerinski.*

1. **Core maintenance for hypergraph streams.** World Wide Web 26(5): 3709-3733 (2023) [[paper]](https://doi.org/10.1007/s11280-023-01196-6) `Exact` `Fully dynamic`

   *Qi Luo, Dongxiao Yu, Zhipeng Cai, Yanwei Zheng, Xiuzhen Cheng, Xuemin Lin.*

1. **Distributed Approaches to Butterfly Analysis on Large Dynamic Bipartite Graphs.** IEEE Trans. Parallel Distributed Syst. 34(2): 431-445 (2023) [[paper]](https://doi.org/10.1109/tpds.2022.3221821) `Exact` `Fully dynamic`

   *Tongfeng Weng, Xu Zhou, Kenli Li, Kian-Lee Tan, Keqin Li.*

1. **Incremental Graph Computation: Anchored Vertex Tracking in Dynamic Social Networks.** IEEE Trans. Knowl. Data Eng. 35(7): 7030-7044 (2023) [[paper]](https://doi.org/10.1109/tkde.2022.3199494) `Approx` `Fully dynamic` `Snapshots`

   *Taotao Cai, Shuiqiao Yang, Jianxin Li, Quan Z. Sheng, Jian Yang, Xin Wang, Wei Emma Zhang, Longxiang Gao.*

1. **Quantifying Node Importance over Network Structural Stability.** KDD 2023: 3217-3228 [[paper]](https://doi.org/10.1145/3580305.3599480) `Exact` `Fully dynamic`

   *Fan Zhang, Qingyuan Linghu, Jiadong Xie, Kai Wang, Xuemin Lin, Wenjie Zhang.*

1. **Hierarchical core maintenance on large dynamic graphs.** Proc. VLDB Endow. 14(5): 757-770 (2021) [[paper]](https://www.vldb.org/pvldb/vol14/p757-zhang.pdf) `Exact` `Fully dynamic`

   *Zhe Lin, Fan Zhang, Xuemin Lin, Wenjie Zhang, Zhihong Tian.*

1. **Parallel and Streaming Algorithms for K-Core Decomposition.** ICML 2018: 1397-1406 [[paper]](https://proceedings.mlr.press/v80/esfandiari18a.html) `Approx` `Insert-only`

   *Hossein Esfandiari, Silvio Lattanzi, Vahab Mirrokni.*

1. **A Fast Order-Based Approach for Core Maintenance.** ICDE 2017: 337-348 [[paper]](https://doi.org/10.1109/icde.2017.93) `Exact` `Fully dynamic`

   *Yikai Zhang, Jeffrey Xu Yu, Ying Zhang, Lu Qin.*

1. **Incremental k-core decomposition: algorithms and evaluation.** VLDB J. 25(3): 425-447 (2016) [[paper]](https://doi.org/10.1007/s00778-016-0423-8) `Exact` `Fully dynamic`

   *Ahmet Erdem Sariyüce, Buğra Gedik, Gabriela Jacques-Silva, Kun-Lung Wu, Ümit V. Çatalyürek.*

1. **Efficient Core Maintenance in Large Dynamic Graphs.** IEEE Trans. Knowl. Data Eng. 26(10): 2453-2465 (2014) [[paper]](https://doi.org/10.1109/tkde.2013.158) `Exact` `Fully dynamic`

   *Rong-Hua Li, Jeffrey Xu Yu, Rui Mao.*

1. **Streaming algorithms for k-core decomposition.** Proc. VLDB Endow. 6(6): 433-444 (2013) [[paper]](https://www.vldb.org/pvldb/vol6/p433-sariyuce.pdf) `Exact` `Fully dynamic`

   *Ahmet Erdem Sariyüce, Buğra Gedik, Gabriela Jacques-Silva, Kun-Lung Wu, Ümit V. Çatalyürek.*

### [Dense Subgraph](#content)

1. **New Parallel and Streaming Algorithms for Directed Densest Subgraph.** NeurIPS 2025: 40441-40465 [[paper]](https://doi.org/10.52202/085713-1209) `Approx` `Insert-only`

   *Slobodan Mitrovic, Theodore Pan, Mahdi Qaempanah, Mohammad Amin Raeisi.*

1. **Approximate Anchored Densest Subgraph Search on Large Static and Dynamic Graphs.** Proc. VLDB Endow. 18(3): 623-636 (2024) [[paper]](https://www.vldb.org/pvldb/vol18/p623-li.pdf) [[code]](https://github.com/qizhang1996/aads) `Approx` `Fully dynamic`

   *Qi Zhang, Yalong Zhang, Rong-Hua Li, Guoren Wang.*

1. **Faster Streaming and Scalable Algorithms for Finding Directed Dense Subgraphs in Large Graphs.** ICML 2024: 35876-35891 [[paper]](https://proceedings.mlr.press/v235/mitrovic24a.html) `Approx` `Insert-only`

   *Slobodan Mitrovic, Theodore Pan.*

1. **Spade+: A Generic Real-Time Fraud Detection Framework on Dynamic Graphs.** IEEE Trans. Knowl. Data Eng. 36(11): 7058-7073 (2024) [[paper]](https://doi.org/10.1109/tkde.2024.3394155) `Approx` `Fully dynamic`

   *Jiaxin Jiang, Yuhang Chen, Bingsheng He, Min Chen, Jia Chen.*

1. **Spade: A Real-Time Fraud Detection Framework on Evolving Graphs.** Proc. VLDB Endow. 16(3): 461-469 (2022) [[paper]](https://www.vldb.org/pvldb/vol16/p461-jiang.pdf) [[code]](https://github.com/samjjx/Spade) `Approx` `Insert-only`

   *Jiaxin Jiang, Yuan Li, Bingsheng He, Bryan Hooi, Jia Chen, Johan Kok Zhi Kang.*

1. **Efficient Densest Subgraph Computation in Evolving Graphs.** WWW 2015: 300-310 [[paper]](https://doi.org/10.1145/2736277.2741638) `Approx` `Fully dynamic`

   *Alessandro Epasto, Silvio Lattanzi, Mauro Sozio.*

### [Community Detection](#content)

1. **Communities in Streaming Graphs: Small Space Data Structure, Benchmark Data Generation, and Linear Algorithm.** ACM Trans. Knowl. Discov. Data 19(5): 110:1-110:24 (2025) [[paper]](https://doi.org/10.1145/3735976) [[code]](https://github.com/shubhamgpt007/Streaming-Community-Detection) `Approx` `Insert-only`

   *Shubham Gupta, Suman Kundu.*

1. **Streaming Local Community Detection Through Approximate Conductance.** IEEE Trans. Big Data 10(1): 12-22 (2024) [[paper]](https://doi.org/10.1109/tbdata.2023.3310251) `Approx` `Insert-only`

   *Meng Wang, Yanhao Yang, David Bindel, Kun He.*

1. **Rapid Detection of Local Communities in Graph Streams.** IEEE Trans. Knowl. Data Eng. 34(5): 2375-2386 (2022) [[paper]](https://doi.org/10.1109/tkde.2020.3012608) `Approx` `Insert-only`

   *Panagiotis Liakos, Katia Papakonstantinopoulou, Alexandros Ntoulas, Alex Delis.*

1. **Community Detection in Graph Streams by Pruning Zombie Nodes.** PAKDD 2017: 574-585 [[paper]](https://doi.org/10.1007/978-3-319-57454-7_45) `Approx` `Insert-only`

   *Yue Ding, Ling Huang, Chang-Dong Wang, Dong Huang.*

1. **Dynamic Community Detection in Weighted Graph Streams.** SDM 2013: 151-161 [[paper]](https://doi.org/10.1137/1.9781611972832.17) `Approx` `Insert-only`

   *Chang-Dong Wang, Jian-Huang Lai, Philip S. Yu.*

### [Community Search](#content)

1. **Finding Time-Proximity Communities in Temporal Heterogeneous Information Networks.** Proc. VLDB Endow. 18(13): 5740-5752 (2025) [[paper]](https://www.vldb.org/pvldb/vol18/p5740-tang.pdf) [[code]](https://github.com/Craig-Tang/THCS) `Exact` `Insert-only`

   *Yifu Tang, Chengfei Liu, Lu Chen, Rui Zhou, Jianxin Li.*

1. **Truss-Based Community Search over Streaming Directed Graphs.** Proc. VLDB Endow. 17(8): 1816-1829 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p1816-xu.pdf) `Exact` `Sliding window`

   *Xuankun Liao, Qing Liu, Xin Huang, Jianliang Xu.*

1. **Discovering Significant Communities on Bipartite Graphs: An Index-based Approach.** IEEE Trans. Knowl. Data Eng. 35(3): 2471-2485 (2023) [[paper]](https://doi.org/10.1109/tkde.2021.3111349) `Exact` `Fully dynamic`

   *Kai Wang, Wenjie Zhang, Ying Zhang, Lu Qin, Yuting Zhang.*

1. **Searching Personalized k-Wing in Bipartite Graphs.** IEEE Trans. Knowl. Data Eng. 35(8): 8515-8528 (2023) [[paper]](https://doi.org/10.1109/tkde.2022.3199592) `Exact` `Fully dynamic`

   *Aman Abidi, Lu Chen, Rui Zhou, Chengfei Liu.*

1. **Reliable Community Search in Dynamic Networks.** Proc. VLDB Endow. 15(11): 2826-2838 (2022) [[paper]](https://www.vldb.org/pvldb/vol15/p2826-li.pdf) [[code]](https://github.com/Cyril-Tang/CRC-query) `Exact` `Fully dynamic` `Snapshots`

   *Yifu Tang, Jianxin Li, Nur Al Hasan Haldar, Ziyu Guan, Jiajie Xu, Chengfei Liu.*

1. **Querying k-truss community in large and dynamic graphs.** SIGMOD Conference 2014: 1311-1322 [[paper]](https://doi.org/10.1145/2588555.2610495) `Exact` `Fully dynamic`

   *Xin Huang, Hong Cheng, Lu Qin, Wentao Tian, Jeffrey Xu Yu.*

### [Graph Clustering](#content)

1. **Efficient processing of streaming graphs for evolution-aware clustering.** CIKM 2013: 319-328 [[paper]](https://doi.org/10.1145/2505515.2505750) `Approx` `Insert-only` `Sliding window`

   *Mindi Yuan, Kun-Lung Wu, Gabriela Jacques-Silva, Yi Lu.*

1. **Clustering Streaming Graphs.** ICDCS 2012: 466-475 [[paper]](https://doi.org/10.1109/icdcs.2012.20) `Approx` `Fully dynamic` `Sliding window`

   *Ahmed Eldawy, Rohit Khandekar, Kun-Lung Wu.*

1. **On Clustering Graph Streams.** SDM 2010: 478-489 [[paper]](https://doi.org/10.1137/1.9781611972801.42) `Approx` `Insert-only`

   *Charu C. Aggarwal, Yuchen Zhao, Philip S. Yu.*

## [Graph Analytics](#content)

1. **Identifying influential vertices with top-K largest temporal katz centralities in a streaming graph using constant memory.** Expert Syst. Appl. 296: 128943 (2026) [[paper]](https://doi.org/10.1016/j.eswa.2025.128943) `Approx` `Insert-only`

   *Jiaming Zhang, Qingjun Xiao, Jun Ma, Liukun He, Qifan Zhang, Guang Cheng.*

1. **Efficient Index Maintenance for Effective Resistance Computation on Evolving Graphs.** Proc. ACM Manag. Data 3(1): 36:1-36:27 (2025) [[paper]](https://doi.org/10.1145/3709686) [[code]](https://github.com/mhliao0516/LEindex) `Approx` `Fully dynamic`

   *Meihao Liao, Cheng Li, Rong-Hua Li, Guoren Wang.*

1. **Real-Time Single-Source Personalized PageRank Over Evolving Social Networks.** ICDE 2025: 3765-3777 [[paper]](https://doi.org/10.1109/icde65448.2025.00281) [[code]](https://github.com/SujunShuai/Work2023) `Approx` `Fully dynamic`

   *Sujun Shuai, Xuan Rao, Lisi Chen, Shuo Shang, Shen Gao.*

1. **Semi-Streaming Algorithms for Hypergraph Matching.** ESA 2025: 79:1-79:19 [[paper]](https://doi.org/10.4230/LIPIcs.ESA.2025.79) [[code]](https://github.com/HeiHGM/Streaming) `Approx` `Insert-only`

   *Henrik Reinstädtler, S. M. Ferdous, Alex Pothen, Bora Uçar, Christian Schulz.*

1. **Influence Maximization via Vertex Countering.** Proc. VLDB Endow. 17(6): 1297-1309 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p1297-zhang.pdf) [[code]](https://github.com/mao-qiu/countering) `Approx` `Fully dynamic`

   *Jiadong Xie, Zehua Chen, Deming Chu, Fan Zhang, Xuemin Lin, Zhihong Tian.*

1. **Querying Structural Diversity in Streaming Graphs.** Proc. VLDB Endow. 17(5): 1034-1046 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p1034-wen.pdf) [[code]](https://github.com/kevinChnn/structural-diversity-queries) `Exact` `Insert-only` `Sliding window`

   *Kaiyu Chen, Dong Wen, Wenjie Zhang, Ying Zhang, Xiaoyang Wang, Xuemin Lin.*

1. **Everything Evolves in Personalized PageRank.** WWW 2023: 3342-3352 [[paper]](https://doi.org/10.1145/3543507.3583474) [[code]](https://github.com/DongqiFu/EvePPR) `Approx` `Fully dynamic` `Snapshots`

   *Zihao Li, Dongqi Fu, Jingrui He.*

1. **Personalized PageRank on Evolving Graphs with an Incremental Index-Update Scheme.** Proc. ACM Manag. Data 1(1): 25:1-25:26 (2023) [[paper]](https://doi.org/10.1145/3588705) [[code]](https://github.com/lalumine/firm) `Approx` `Fully dynamic`

   *Guanhao Hou, Qintian Guo, Fangyuan Zhang, Sibo Wang, Zhewei Wei.*

1. **Space-efficient random walks on streaming graphs.** Proc. VLDB Endow. 16(2): 356-368 (2022) [[paper]](https://www.vldb.org/pvldb/vol16/p356-papadias.pdf) [[code]](https://github.com/spapadias/wharf) `Exact` `Fully dynamic`

   *Serafeim Papadias, Zoi Kaoudi, Jorge-Arnulfo Quiané-Ruiz, Volker Markl.*

1. **A Fast Sketch Method for Mining User Similarities Over Fully Dynamic Graph Streams.** ICDE 2019: 1682-1685 [[paper]](https://doi.org/10.1109/icde.2019.00172) `Approx` `Fully dynamic`

   *Peng Jia, Pinghui Wang, Jing Tao, Xiaohong Guan.*

1. **Sampling for Approximate Bipartite Network Projection.** IJCAI 2018: 3286-3292 [[paper]](https://doi.org/10.24963/ijcai.2018/456) `Approx` `Insert-only`

   *Nesreen K. Ahmed, Nick Duffield, Liangzhen Xia.*

1. **Approximate Personalized PageRank on Dynamic Graphs.** KDD 2016: 1315-1324 [[paper]](https://doi.org/10.1145/2939672.2939804) `Approx` `Fully dynamic`

   *Hongyang Zhang, Peter Lofgren, Ashish Goel.*

1. **Efficient PageRank Tracking in Evolving Networks.** KDD 2015: 875-884 [[paper]](https://doi.org/10.1145/2783258.2783297) `Approx` `Fully dynamic`

   *Naoto Ohsaka, Takanori Maehara, Ken-ichi Kawarabayashi.*

1. **Fully dynamic betweenness centrality maintenance on massive networks.** Proc. VLDB Endow. 9(2): 48-59 (2015) [[paper]](https://www.vldb.org/pvldb/vol9/p48-hayashi.pdf) `Approx` `Fully dynamic`

   *Takanori Hayashi, Takuya Akiba, Yuichi Yoshida.*

1. **Fast incremental and personalized PageRank.** Proc. VLDB Endow. 4(3): 173-184 (2010) [[paper]](https://www.vldb.org/pvldb/vol4/p173-bahmani.pdf) `Approx` `Fully dynamic`

   *Bahman Bahmani, Abdur Chowdhury, Ashish Goel.*

## [Anomaly & Event Detection](#content)

### [Anomaly Detection](#content)

1. **Anomaly Detection of Interaction Behaviors in Streaming Graphs.** WWW 2026: 879-890 [[paper]](https://doi.org/10.1145/3774904.3792282) `Approx` `Fully dynamic`

   *Shuai Ren, Fan Zhang, Bolin Wang, Xiang Zhao, Zhihong Tian.*

1. **STG-DGR: Fraud Detection on Streaming Transaction Graphs with Diffusion-based Generative Replay.** WWW 2026: 742-753 [[paper]](https://doi.org/10.1145/3774904.3792195) `Snapshots`

   *Rui Ou, Kun Zhu, Nana Zhang, Jiangtong Li, Chaochao Chen, Changjun Jiang.*

1. **FiFrauD: Unsupervised Financial Fraud Detection in Dynamic Graph Streams.** ACM Trans. Knowl. Discov. Data 18(5): 111:1-111:29 (2024) [[paper]](https://doi.org/10.1145/3641857) `Approx` `Snapshots`

   *Samira Khodabandehlou, Alireza Hashemi Golpayegani.*

1. **SLADE: Detecting Dynamic Anomalies in Edge Streams without Labels via Self-Supervised Learning.** KDD 2024: 1506-1517 [[paper]](https://doi.org/10.1145/3637528.3671845) `Insert-only`

   *Jongha Lee, Sunwoo Kim, Kijung Shin.*

1. **Anonymous Edge Representation for Inductive Anomaly Detection in Dynamic Bipartite Graph.** Proc. VLDB Endow. 16(5): 1154-1167 (2023) [[paper]](https://www.vldb.org/pvldb/vol16/p1154-fang.pdf) [[code]](https://github.com/fanglanting/AER) `Insert-only`

   *Lanting Fang, Kaiyu Feng, Jie Gui, Shanshan Feng, Aiqun Hu.*

1. **Example-based explanations for streaming fraud detection on graphs.** Inf. Sci. 621: 319-340 (2023) [[paper]](https://doi.org/10.1016/j.ins.2022.11.119) `Insert-only`

   *Thanh Tam Nguyen, Thanh Cong Phan, Hien Thu Pham, Thanh Thi Nguyen, Jun Jo, Quoc Viet Hung Nguyen.*

1. **Sketch-Based Anomaly Detection in Streaming Graphs.** KDD 2023: 93-104 [[paper]](https://doi.org/10.1145/3580305.3599504) [[code]](https://github.com/Stream-AD/AnoGraph) `Approx` `Insert-only`

   *Siddharth Bhatia, Mohit Wadhwa, Kenji Kawaguchi, Neil Shah, Philip S. Yu, Bryan Hooi.*

1. **MonLAD: Money Laundering Agents Detection in Transaction Streams.** WSDM 2022: 976-986 [[paper]](https://doi.org/10.1145/3488560.3498418) [[code]](https://github.com/BGT-M/MonLAD) `Approx` `Insert-only` `Sliding window`

   *Xiaobing Sun, Wenjie Feng, Shenghua Liu, Yuyang Xie, Siddharth Bhatia, Bryan Hooi, Wenhan Wang, Xueqi Cheng.*

1. **Real-Time Anomaly Detection in Edge Streams.** ACM Trans. Knowl. Discov. Data 16(4): 75:1-75:22 (2022) [[paper]](https://doi.org/10.1145/3494564) [[code]](https://github.com/Stream-AD/MIDAS) `Approx` `Insert-only`

   *Siddharth Bhatia, Rui Liu, Bryan Hooi, Minji Yoon, Kijung Shin, Christos Faloutsos.*

1. **F-FADE: Frequency Factorization for Anomaly Detection in Edge Streams.** WSDM 2021: 589-597 [[paper]](https://doi.org/10.1145/3437963.3441806) [[code]](https://github.com/snap-stanford/F-FADE) `Approx` `Insert-only`

   *Yen-Yu Chang, Pan Li, Rok Sosic, M. H. Afifi, Marco Schweighauser, Jure Leskovec.*

1. **MIDAS: Microcluster-Based Detector of Anomalies in Edge Streams.** AAAI 2020: 3242-3249 [[paper]](https://doi.org/10.1609/aaai.v34i04.5724) [[code]](https://github.com/bhatiasiddharth/MIDAS) `Approx` `Insert-only`

   *Siddharth Bhatia, Bryan Hooi, Minji Yoon, Kijung Shin, Christos Faloutsos.*

1. **Fast and Accurate Anomaly Detection in Dynamic Graphs with a Two-Pronged Approach.** KDD 2019: 647-657 [[paper]](https://doi.org/10.1145/3292500.3330946) [[code]](https://github.com/minjiyoon/anomrank) `Approx` `Fully dynamic`

   *Minji Yoon, Bryan Hooi, Kijung Shin, Christos Faloutsos.*

1. **SedanSpot: Detecting Anomalies in Edge Streams.** ICDM 2018: 953-958 [[paper]](https://doi.org/10.1109/icdm.2018.00117) [[code]](https://github.com/dhivyaeswaran/sedanspot) `Approx` `Insert-only`

   *Dhivya Eswaran, Christos Faloutsos.*

1. **SpotLight: Detecting Anomalies in Streaming Graphs.** KDD 2018: 1378-1386 [[paper]](https://doi.org/10.1145/3219819.3220040) `Approx` `Snapshots`

   *Dhivya Eswaran, Christos Faloutsos, Sudipto Guha, Nina Mishra.*

1. **Fast Memory-efficient Anomaly Detection in Streaming Heterogeneous Graphs.** KDD 2016: 1035-1044 [[paper]](https://doi.org/10.1145/2939672.2939783) `Approx` `Insert-only`

   *Emaad Manzoor, Sadegh M. Milajerdi, Leman Akoglu.*

1. **On Anomalous Hotspot Discovery in Graph Streams.** ICDM 2013: 1271-1276 [[paper]](https://doi.org/10.1109/icdm.2013.32) `Approx` `Insert-only`

   *Weiren Yu, Charu C. Aggarwal, Shuai Ma, Haixun Wang.*

1. **Outlier detection in graph streams.** ICDE 2011: 399-409 [[paper]](https://doi.org/10.1109/icde.2011.5767885) `Approx` `Insert-only`

   *Charu C. Aggarwal, Yuchen Zhao, Philip S. Yu.*

### [Burst & Event Detection](#content)

1. **RUSH: Real-Time Burst Subgraph Detection in Dynamic Graphs.** Proc. VLDB Endow. 17(11): 3657-3665 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p3657-chen.pdf) [[code]](https://github.com/Xtra-Computing/RUSH) `Approx` `Insert-only`

   *Yuhang Chen, Jiaxin Jiang, Shixuan Sun, Bingsheng He, Min Chen.*

1. **Discovering Bursting Patterns over Streaming Graphs.** DASFAA 2022: 441-458 [[paper]](https://doi.org/10.1007/978-3-031-00123-9_36) `Approx` `Insert-only`

   *Qianzhen Zhang, Deke Guo, Xiang Zhao.*

1. **Tracking triadic cardinality distributions for burst detection in high-speed graph streams.** Knowl. Inf. Syst. 63(4): 939-969 (2021) [[paper]](https://doi.org/10.1007/s10115-021-01543-x) `Approx` `Insert-only`

   *Junzhou Zhao, Pinghui Wang, Zhouguo Chen, Jianwei Ding, John C. S. Lui, Don Towsley, Xiaohong Guan.*

1. **Event pattern discovery by keywords in graph streams.** IEEE BigData 2017: 982-987 [[paper]](https://doi.org/10.1109/bigdata.2017.8258019) `Exact` `Snapshots`

   *Mohammad Hossein Namaki, Peng Lin, Yinghui Wu.*

### [Concept Drift](#content)

1. **An Approach For Concept Drift Detection in a Graph Stream Using Discriminative Subgraphs.** ACM Trans. Knowl. Discov. Data 14(6): 70:1-70:25 (2020) [[paper]](https://doi.org/10.1145/3406243) [[code]](https://github.com/rpaudel42/ds_dd) `Approx` `Sliding window`

   *Ramesh Paudel, William Eberle.*

1. **Concept Drift and Anomaly Detection in Graph Streams.** IEEE Trans. Neural Networks Learn. Syst. 29(11): 5592-5605 (2018) [[paper]](https://doi.org/10.1109/tnnls.2018.2804443) `Approx` `Insert-only`

   *Daniele Zambon, Cesare Alippi, Lorenzo Livi.*

## [Learning on Streaming Graphs](#content)

### [Representation Learning](#content)

1. **Incremental GNN Embedding Computation on Streaming Graphs.** ICDE 2026: 2349-2362 [[paper]](https://doi.org/10.1109/icde65706.2026.00176) `Fully dynamic`

   *Qiange Wang, Haoran Lv, Yanfeng Zhang, Weng-Fai Wong, Bingsheng He.*

1. **Spatio-Temporal Fusion in Graph Neural Network for Streaming Knowledge Tracing.** DASFAA 2026: 136-153 [[paper]](https://doi.org/10.1007/978-981-92-0375-8_9) `Insert-only`

   *Yi-Fei Wen, Hang Liang, Carl Yang, Wen-Bo Xie, Yajun Du, Xianyong Li, Yan-Li Lee.*

1. **InkStream: Instantaneous GNN Inference on Dynamic Graphs via Incremental Update.** IPDPS 2025: 1273-1285 [[paper]](https://doi.org/10.1109/ipdps64566.2025.00115) [[code]](https://github.com/WuDan0399/InkStream) `Fully dynamic`

   *Dan Wu, Zhaoying Li, Tulika Mitra.*

1. **Ripple: Scalable Incremental GNN Inferencing on Large Streaming Graphs.** ICDCS 2025: 857-867 [[paper]](https://doi.org/10.1109/icdcs63083.2025.00088) `Fully dynamic`

   *Pranjal Naman, Yogesh Simmhan.*

1. **D3-GNN: Dynamic Distributed Dataflow for Streaming Graph Neural Networks.** Proc. VLDB Endow. 17(11): 2764-2777 (2024) [[paper]](https://www.vldb.org/pvldb/vol17/p2764-guliyev.pdf) [[code]](https://github.com/Rustam-Warwick/d3-gnn) `Fully dynamic`

   *Rustam Guliyev, Aparajita Haldar, Hakan Ferhatosmanoglu.*

1. **Reducing Resource Usage for Continuous Model Updating and Predictive Query Answering in Graph Streams.** ICDE 2024: 2653-2666 [[paper]](https://doi.org/10.1109/icde60146.2024.00208) `Snapshots`

   *Qu Liu, Adam King, Tingjian Ge.*

1. **NeutronStream: A Dynamic GNN Training Framework with Sliding Window for Graph Streams.** Proc. VLDB Endow. 17(3): 455-468 (2023) [[paper]](https://www.vldb.org/pvldb/vol17/p455-chen.pdf) [[code]](https://github.com/iDC-NEU/NeutronStream) `Insert-only`

   *Chaoyi Chen, Dechao Gao, Yanfeng Zhang, Qiange Wang, Zhenbo Fu, Xuecang Zhang, Junhua Zhu, Yu Gu, Ge Yu.*

1. **Streaming Graph Embeddings via Incremental Neighborhood Sketching.** IEEE Trans. Knowl. Data Eng. 35(5): 5296-5310 (2023) [[paper]](https://doi.org/10.1109/tkde.2022.3149999) `Insert-only`

   *Dingqi Yang, Bingqing Qu, Jie Yang, Liang Wang, Philippe Cudré-Mauroux.*

1. **RL2: A Call for Simultaneous Representation Learning and Rule Learning for Graph Streams.** KDD 2022: 1109-1119 [[paper]](https://doi.org/10.1145/3534678.3539309) `Insert-only`

   *Qu Liu, Tingjian Ge.*

1. **Streaming Graph Neural Networks with Generative Replay.** KDD 2022: 1878-1888 [[paper]](https://doi.org/10.1145/3534678.3539336) [[code]](https://github.com/Junshan-Wang/SGNN-GR) `Snapshots`

   *Junshan Wang, Wenhao Zhu, Guojie Song, Liang Wang.*

1. **T-GCN: A Sampling Based Streaming Graph Neural Network System with Hybrid Architecture.** PACT 2022: 69-82 [[paper]](https://doi.org/10.1145/3559009.3569648) `Insert-only`

   *Chengying Huan, Shuaiwen Leon Song, Yongchao Liu, Heng Zhang, Hang Liu, Charles He, Kang Chen, Jinlei Jiang, Yongwei Wu.*

1. **Streaming Dynamic Graph Neural Networks for Continuous-Time Temporal Graph Modeling.** ICDM 2021: 1361-1366 [[paper]](https://doi.org/10.1109/icdm51629.2021.00171) `Insert-only`

   *Sheng Tian, Tao Xiong, Leilei Shi.*

1. **Streaming Graph Neural Networks via Continual Learning.** CIKM 2020: 1515-1524 [[paper]](https://doi.org/10.1145/3340531.3411963) `Snapshots`

   *Junshan Wang, Guojie Song, Yi Wu, Liang Wang.*

1. **Streaming Graph Neural Networks.** SIGIR 2020: 719-728 [[paper]](https://doi.org/10.1145/3397271.3401092) [[code]](https://github.com/alge24/dygnn) `Insert-only`

   *Yao Ma, Ziyi Guo, Zhaocun Ren, Jiliang Tang, Dawei Yin.*

### [Node & Graph Classification](#content)

1. **Simple yet Effective Node Property Prediction on Edge Streams under Distribution Shifts.** ICDE 2025: 2521-2534 [[paper]](https://doi.org/10.1109/icde65448.2025.00190) `Insert-only`

   *Jongha Lee, Taehyung Kwon, Heechan Moon, Kijung Shin.*

1. **PUMA: Efficient Continual Graph Learning for Node Classification With Graph Condensation.** IEEE Trans. Knowl. Data Eng. 37(1): 449-461 (2025) [[paper]](https://doi.org/10.1109/tkde.2024.3485691) [[code]](https://github.com/superallen13/PUMA) `Snapshots`

   *Yilun Liu, Ruihong Qiu, Yanran Tang, Hongzhi Yin, Zi Huang.*

1. **CaT: Balanced Continual Graph Learning with Graph Condensation.** ICDM 2023: 1157-1162 [[paper]](https://doi.org/10.1109/icdm58522.2023.00141) [[code]](https://github.com/superallen13/CaT-CGL) `Snapshots`

   *Yilun Liu, Ruihong Qiu, Zi Huang.*

1. **On Supervised Change Detection in Graph Streams.** SDM 2020: 289-297 [[paper]](https://doi.org/10.1137/1.9781611976236.33) `Sliding window`

   *Charu C. Aggarwal, Yao Li, Philip S. Yu.*

1. **Hashing for Adaptive Real-Time Graph Stream Classification With Concept Drifts.** IEEE Trans. Cybern. 48(5): 1591-1604 (2018) [[paper]](https://doi.org/10.1109/tcyb.2017.2708979) `Insert-only`

   *Lianhua Chi, Bin Li, Xingquan Zhu, Shirui Pan, Ling Chen.*

1. **Graph Ensemble Boosting for Imbalanced Noisy Graph Stream Classification.** IEEE Trans. Cybern. 45(5): 954-968 (2015) [[paper]](https://doi.org/10.1109/tcyb.2014.2341031) `Insert-only`

   *Shirui Pan, Jia Wu, Xingquan Zhu, Chengqi Zhang.*

1. **Graph stream classification using labeled and unlabeled graphs.** ICDE 2013: 398-409 [[paper]](https://doi.org/10.1109/icde.2013.6544842) `Insert-only`

   *Shirui Pan, Xingquan Zhu, Chengqi Zhang, Philip S. Yu.*

1. **On Classification of Graph Streams.** SDM 2011: 652-663 [[paper]](https://doi.org/10.1137/1.9781611972818.56) `Insert-only`

   *Charu C. Aggarwal.*

### [Link Prediction & Recommendation](#content)

1. **GPL4SRec: Graph Multi-Level Aware Prompt Learning for Streaming Recommendation.** IJCAI 2025: 2713-2721 [[paper]](https://doi.org/10.24963/ijcai.2025/302) `Snapshots`

   *Hao Cang, Huanhuan Yuan, Jiaqing Fan, Lei Zhao, Guanfeng Liu, Pengpeng Zhao.*

1. **GPT4Rec: Graph Prompt Tuning for Streaming Recommendation.** SIGIR 2024: 1774-1784 [[paper]](https://doi.org/10.1145/3626772.3657720) `Snapshots`

   *Peiyan Zhang, Yuchen Yan, Xi Zhang, Liying Kang, Chaozhuo Li, Feiran Huang, Senzhang Wang, Sunghun Kim.*

1. **GraphPro: Graph Pre-training and Prompt Learning for Recommendation.** WWW 2024: 3690-3699 [[paper]](https://doi.org/10.1145/3589334.3645546) [[code]](https://github.com/HKUDS/GraphPro) `Snapshots`

   *Yuhao Yang, Lianghao Xia, Da Luo, Kangyi Lin, Chao Huang.*

1. **Dynamically Expandable Graph Convolution for Streaming Recommendation.** WWW 2023: 1457-1467 [[paper]](https://doi.org/10.1145/3543507.3583237) `Snapshots`

   *Bowei He, Xu He, Yingxue Zhang, Ruiming Tang, Chen Ma.*

1. **The Link Regression Problem in Graph Streams.** IEEE BigData 2019: 1088-1095 [[paper]](https://doi.org/10.1109/bigdata47090.2019.9006225) `Insert-only`

   *Bowen Dong, Charu C. Aggarwal, Philip S. Yu.*

1. **Streaming Link Prediction on Dynamic Attributed Networks.** WSDM 2018: 369-377 [[paper]](https://doi.org/10.1145/3159652.3159674) `Insert-only`

   *Jundong Li, Kewei Cheng, Liang Wu, Huan Liu.*

1. **Link prediction in graph streams.** ICDE 2016: 553-564 [[paper]](https://doi.org/10.1109/icde.2016.7498270) `Insert-only`

   *Peixiang Zhao, Charu C. Aggarwal, Gewen He.*

### [Generation & Forecasting](#content)

1. **sGrow: Explaining the Scale-Invariant Strength Assortativity of Streaming Butterflies.** ACM Trans. Web 17(3): 24:1-24:46 (2023) [[paper]](https://doi.org/10.1145/3572408) `Insert-only`

   *Aida Sheshbolouki, M. Tamer Özsu.*

1. **TrafficStream: A Streaming Traffic Flow Forecasting Framework Based on Graph Neural Networks and Continual Learning.** IJCAI 2021: 3620-3626 [[paper]](https://doi.org/10.24963/ijcai.2021/498) [[code]](https://github.com/AprLie/TrafficStream) `Snapshots`

   *Xu Chen, Junshan Wang, Kunqing Xie.*
