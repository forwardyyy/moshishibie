# moshishibie
模式识别
经典三维重建系统的整个pipeline从相机标定、基础矩阵与本质矩阵估计、特征匹配到运动恢复结构（SFM），从SFM到稠密点云重建、表面重建、纹理贴图。
![image](https://user-images.githubusercontent.com/90848881/233792940-203f7ded-66a5-4bc1-b024-94c02a19f1fe.png)
三维重建的 SfM (Structure from Motion) 算法是通过多张二维图片来重建三维场景的算法。

算法实现流程：
特征点提取
在这个步骤中，需要对每张图片提取出一些特征点，并计算它们的描述子。在特征点提取的过程中，可以使用 SIFT，SURF 等算法。一般来说，一个好的特征点需要具备旋转不变性、尺度不变性和灰度不变性。
特征匹配
将不同图片中的特征点进行匹配，找到它们之间的对应关系。可以使用 KNN，FLANN 等算法进行特征匹配。需要注意的是，在匹配的过程中，需要使用一些鲁棒的技巧来避免匹配误差的影响。
相机姿态估计
通过特征点匹配，可以得到不同图片之间的几何变换关系。通过这些变换关系，可以估计出相机的姿态，包括相机的位置和方向。常用的算法包括 RANSAC 算法和 P3P 算法。
三角测量
在相机姿态估计的基础上，通过三角测量的方法来估计场景中每个特征点的三维位置。一般来说，需要使用两个相机的视角来进行三角测量，这个过程叫做三角化。
重建场景
在完成了每张图片的三维重建之后，需要将它们融合起来来构建整个场景的三维模型。可以使用 BA（Bundle Adjustment）等算法对重建结果进行优化。
需要注意的是，由于 SfM 算法是一种迭代的算法，所以在每个步骤中都需要不断地调整参数和优化结果，以获得更加准确和稳定的结果。
————————————————
版权声明：本文为CSDN博主「Hello.Reader」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixin_43114209/article/details/129111394
