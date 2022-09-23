# gym

- [Windows,Linux,macOS三平台安装OpenAI的Gym和Universe](https://www.jianshu.com/p/536d300a397e/)
- [Exploring OpenAI Gym: A Platform for Reinforcement Learning Algorithms](https://www.velotio.com/engineering-blog/exploring-openai-gym)
- [OpenAI Gym 多线程环境的简单实现，适用于A2C、A3C等算法](https://blog.csdn.net/qq_33361420/article/details/121157881)
- [OpenAI gym tutorial](https://ai-mrkogao.github.io/reinforcement%20learning/openaigymtutorial/)
- 

*****************************

安装 gym 之前先要安装 anaconda, 其安装参见 
[pytorch 安装时的 anaconda 安装](pytorch.md#anaconda)


1. 管理员运行进入 anaconda
2. git clone https://github.com/openai/gym.git
3. 进入下载好的 gym 文件夹
4. 激活环境 conda activate env_pytorch
5. pip install gym \
   此时立刻运行 pip install gym[Box2d] 会报错
6. conda install swig
7. pip install gym[Box2d]





