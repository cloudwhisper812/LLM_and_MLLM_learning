# Qwen3 

## Pre-training stage
分成3个stages：
（1）30T数据，sequence length 4096 
（2）用专业性知识STEM, coding, reasoning, synthetic data来训练模型.5T数据，sequence length 4096。 
（3）Max sequence length 32768. 不同长度混合。和2.5一样修改基频，并且在infer的时候用 DCA, YARN.
