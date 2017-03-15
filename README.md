 https://translate.googleusercontent.com/translate_c?depth=1&hl=en&ie=UTF8&prev=_t&rurl=translate.google.com&sl=zh-CN&sp=nmt4&tl=en&u=https://github.com/willard-yuan/hashing-baseline-for-image-retrieval&usg=ALkJrhiUgfJ27OtbiKo69orWhH95ryhdCg
 
 What is the HABIR Hash Image Retrieval Toolkit?

The HABIR Hash Image Retrieval Toolbox is a benchmark framework that incorporates a classic hash method in Matlab language and an unsupervised hash method in recent years, which includes a mainstream evaluation index for image retrieval that makes use of the toolbox Can focus on the design of the hash method, and other performance evaluations of these aspects can be done by it to help you complete.

 Why is there a HABIR Hash Image Retrieval Toolbox?

At present, I am mainly committed to large-scale image retrieval research, in the image retrieval in addition to focus and duplicate search I also spent a lot of effort in the hash large-scale image retrieval. In the course of the study, I found that very few researchers provided different combinations of code. This is a great deal of inconvenience for the study, and I firmly believe that in the course of the study, we should focus on the design of the new algorithm, rather than new people have to re-create the wheels, we can learn on the basis of existing code And it is extended for their own use. So there's the hashing-baseline-for-image-retrieval you've seen now, and hopefully it's a little help for small partners who are interested in image retrieval based on the hash method. If you want to understand the hash, then a summary of the blog here is very helpful to you: Hashing image retrieval source and database summary

 How do I use the HABIR Hash Image Retrieval Toolbox?

Download the database. On the local computer, the HABIR file directory structure is shown in the following figure:
Precision-recall-64bits

Figure 1 Toolkit directory

Precision-recall-64bits

Figure 2 CIFAR-10 image database directory

You can see these four feature files are relatively large, these four files can be downloaded to the following link to download, please download the directory according to Figure 1 placed.

256feat4096Norml.mat Download: 256feat4096Norml.mat 
Cifar10-Gist512.mat Download: Cifar10-Gist512.mat 
Caltech256-CNN1024dNorml.mat Download: Caltech256-CNN1024dNorml.mat 
cifar_10yunchao.mat Download: cifar_10yunchao.mat 

Place the DB-FeaturesToBeProcessing data in the DB-FeaturesToBeProcessing folder. Another relatively large file is CIFAR-10 database, the image of the database go to the official website to download the corresponding version of Matlab, after decompression according to Figure 2 placed.

Note : For CNN feature extraction , you can use a code that I have written with a VGG training to extract CNN features, CNN-for-Image-Retrieval .

2. Run the script. The toolbox has three executable scripts, each script corresponds to the following functions:

Main_demo.m: main script file, this is the main script ufor evaluate the performance, and you can get Precision-Recall curve, mean Average Precision (mAP) curves, Recall-the number of retrieved samples curve, Precision- (Steal lazy, take the English notes I wrote in the script)
Visualize_retrieval_demo.m: Retrieve visualization script files, mainly used to retrieve the results of different query visualization ( the script is still finishing).
Cifar10_10class_visualization.m: Visualize the image on the CIFAR-10 database. The official website CIFAR-10 database provides a mat file saved as a pixel value, which allows you to visualize the image on the database.
 Hashing into the HABIR Hash Image Retrieval Toolbox

PCA-ITQ , PCA-RR : Iterative Quantization. The details of the project created by the author are here: ITQ .

Yunchao Gong and Svetlana Lazebnik. Iterative Quantization: A Procrustean Approach to Learning Binary Codes. In: IEEE International Conference on Computer Vision and Pattern Recognition (CVPR), 2011.
SH : Spectral Hashing. The details of the project created by the author are here: SH .

Y. Weiss, A. Torralba, R. Fergus. Advances in Neural Information Processing Systems, 2008.
SpH : Spherical Hashing. Details of the project created by the author are available here: SpH .

Jae-Pil Heo, Youngwoon Lee, Junfeng He, Shih-Fu Chang, and Sung-eui Yoon. Spherical Hashing. CVPR, 2012.
LSH : Local Sensentive Hashing, classic method.

SKLSH : Maxim Raginsky and Svetlana Lazebnik.

Locality-sensitive binary codes from shift-invariant kernels. Advances in Neural Information Processing 22, pp. 1509-1517, 2009.
PCAH : PCA Hashing.

DSH : Density Sensitive Hashing. Project Homepage Please move here: DSH .

Z. Jin, C. Li, Y. Lin and D. Cai, "Density sensitivity hashing," IEEE Transactions on Cybernetics, 44 (8), pp. 1362-1371.
CBE : Circulant Binary Embedding.

X. Yu, S. Kumar, Y. Gong, SF Chang. Circulant Binary Embedding. In Proceedings of the International Conference on Machine Learning (ICML), 2014.
SELVE : Sparse Embedding and Least Variance Encoding

X. Zhu, L. Zhang and Z. Huang, "A Sparse Embedding and Least Variance Encoding Approach to Hashing," IEEE Transactions on Image Processing, 2014.
In addition to these methods, there are also dengcai78 Unsupervised .

Note : If you want to add SELVE to the contrast, please keep your version of Matlab in 2012 and below, very important .

 V2.0 version of the results demo

V2.0 version of the demo results are as follows, the left is the Precision-Recall curve, the middle of Recall-the number of retrieved samples curve, the right is Precision-the number of retrieved samples Curve:

Precision-recall-64bits

Figure 3: 128-bit encoding

Precision-recall-64bits

Figure 4: 64-bit encoding

Precision-recall-64bits

Figure 5: 32-bit encoding

Precision-recall-64bits

Figure 6: 16-bit encoding

Precision-recall-64bits

Figure 7: 8-bit encoding

Precision-recall-64bits

Figure 8: mAP curve at different coding bits (run times = 1)

Tips : In order to polish the picture, it is recommended that you use Adobe Illustrator to deal with it makes it more beautiful.

 V1.x version of the results demo

V1.x version of the demo results are as follows, in the 64-bit code, the precision and recall rate curve is as follows:

Precision-recall-64bits

In the 8-bit code, the recall rate is as follows:

Recall-8bits

The average retrieval accuracy of MAP varies with the length of the bits

Map-numbers-of-bits

Retrieve the instance

Horse

Horse

Horse

Horse

 Operating environment

Matlab
 Need to pay attention to the place

For errors such as Error using eigs/checkInputs (line 567) during SELVE operation, see the description of Notice in SELVE , thanks to @xysoul.

 new version update

V2.0 2015/06/10
Compared to the 1.x version, the version made a larger update, adding a new evaluation index, the basic coverage of the paper commonly used in the above mentioned four indicators.
Made some adjustments to the framework, and added the 2014 related papers.
V1.4 2014/09/22
Repair the MAP curve error, re-use Gong Yunchao used to calculate the curve area method MAP curve
(10 times, the program can modify their own settings), the 10 times the MAP to take the average, the reason for doing so because of different methods used in the random function, through the use of the original function of the curve Run several times to reduce the difference in the results of each run
V1.3 2014/08/21
Complete the MAP with the length of the curve, added to the SpH and DSH.
Perfect drawing of the map, so that the drawing of the picture more beautiful.
Optimize the frame structure so that the layout is more hierarchical.
V1.2 Molding version: 2014/08/16 --- 2014/08/19
V1.1 initial version: 2013/09/26
V1.0 prototype version: 2013/07/22
 Quotes

If you think this toolkit is useful to you, you can do some of the work of the corresponding reference, I would be very grateful:

Latent Semantic Minimal Hashing for Image Retrieval, published a periodical article:

  @ Divicle {lu2016latent,
   Title = {Latent Semantic Minimal Hashing for Image Retrieval},
   Author = {Lu, Xiaoqiang and Zheng, Xiangtao and Li, Xuelong}
   Journal = {IEEE Transactions on Image Processing},
   Year = {2016}
   Publisher = {IEEE}
 } 
Learning hash functions using sparse reconstruction, research two during their own writing a meeting article:

  @inproceedings {yuan2014learning,
   Title = {Learning hash functions using sparse reconstruction},
   Author = {Yuan, Yong and Lu, Xiaoqiang and Li, Xuelong}
   Booktitle = {Proceedings of International Conference on Internet Multimedia Computing and Service},
   Pages = {14},
   Year = {2014},
   Organization = {ACM}
 } 
Compact Structure Hashing via Sparse and Similarity Preserving Embedding, one of the journals that contributed to the paper during the study period:

  @article {ye2016compact,
   Title = {Compact Structure Hashing via Sparse and Similarity Preserving Embedding},
   Author = {Ye, Renzhen and Li, Xuelong},
   Journal = {IEEE transactions on cybernetics},
   Volume = {46},
   Number = {3},
   Pages = {718--729},
   Year = {2016}
   Publisher = {IEEE}
 } 
 contribution

If you think this is useful to you and would like to join in, you can clone the past and then Pull Requests.
