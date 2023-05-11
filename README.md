# awesome-streaming-graphs
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
</tr>
<tr><td colspan="2"><a href="#approximation-algorithms">6. Approximation Algorithms</a></td></tr>
<tr>
    <td>&ensp;<a href="#triangle-count">6.1 Triangle Count</a></td>
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

1. **Time Constrained Continuous Subgraph Search Over Streaming Graphs.** ICDE 2019: 1082-1093 [[paper]](https://ieeexplore.ieee.org/document/8731446)

   *Youhuan Li, Lei Zou, M. Tamer Özsu, Dongyan Zhao.* 
   
1. **A Selectivity based approach to Continuous Pattern Detection in Streaming Graphs.** EDBT 2015: 157-168 [[paper]](https://openproceedings.org/2015/conf/edbt/paper-307.pdf) [[slides]](https://sutanay.github.io/publications/StreamWorks_BlueHat.pdf)

   *Sutanay Choudhury, Lawrence B. Holder, George Chin Jr., Khushbu Agarwal, John Feo.* 

## [Approximation Algorithms](#content)

### [Triangle Count](#content) 

1. **Sliding Window-based Approximate Triangle Counting over Streaming Graphs with Duplicate Edges.** SIGMOD Conference 2021: 645-657 [[paper]](https://dl.acm.org/doi/10.1145/3448016.3452800)

   *Xiangyang Gou, Lei Zou.* 
   
1. **Memory-Efficient and Accurate Sampling for Counting Local Triangles in Graph Streams: From Simple to Multigraphs.** ACM Trans. Knowl. Discov. Data 12(1): 4:1-4:28 (2018) [[paper]](https://dl.acm.org/doi/10.1145/3022186)

   *Yongsub Lim, Minsoo Jung, U Kang.* 
   
1. **TRIÈST: Counting Local and Global Triangles in Fully-Dynamic Streams with Fixed Memory Size..** KDD 2016: 825-834 [[paper]](https://dl.acm.org/doi/10.1145/2939672.2939771)

   *Lorenzo De Stefani, Alessandro Epasto, Matteo Riondato, Eli Upfal.* 
 
