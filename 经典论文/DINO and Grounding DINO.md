看qwen的时候发现有用到grounding dino来造数据：比如用stabel diffusion生成没见过的object（有翅膀的猫），然后用grounding dino做object detetion，最后用sam做分割。

# DINO
主要是特征学习，类似moco做对比学习然后用特征做few shot之类的任务。
模型是vit，有一个teacher和student，teacher输入gloabl view图，student输入同一个图的global view或者local view。
要求student的cls token经过mlp分类和teacher的cls token经过mlp的cross entropy小。
teacher model的vit和mlp都是student model的moving average。
用最后一层的cls做query，去看全图的attention map的话，能正好看到object的分割。它证明了纯无监督的 ViT 也能拥有极其变态的“像素级空间感知（Spatial Awareness）”和物体边界感。


# grouding DINO

### 模型结构
还是离不开detr的思想
1. 图片和文本分别过encoder（swin和bert），得到tokens_i, tokens_t.
2. 两组tokens做feature enhacer。互相做cross attnetion，维度不变。
3. 计算融合后的数据特征和文本特征的点乘相似度，显出最高的一些作为object query的初始化。
4. object query 去和tokens_i, tokens_t做cross attention。
5. querys分别进两个mlp头，一个预测bbox，另一个和之前的tokens_t做点积，得到分类logits。
6. 还是bipartite matching，找到和输入名词最匹配的框，做l1和giou loss。上面的logits和对应的class_labels做contrastive loss，强迫和对应文本的token相似度高。对于那些没有匹配上的背景框，要求和所有token都距离远。


### 训练数据收集
