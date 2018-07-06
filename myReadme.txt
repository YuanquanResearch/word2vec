# 生成词向量文件
./word2vec -train ../w2v/data/0517_0617.filter -output vectors.bin –min-count 10 -cbow 0 -size 100 -window 5 -negative 0 -hs 1 -sample 1e-3 -threads 12 -binary 1

# 生成聚类文件并排序
./word2vec -train ../w2v/data/0517_0617.filter -output classes.txt –min-count 10 -cbow 0 -size 100 -window 5 -negative 0 -hs 1 -sample 1e-3 -threads 12 -classes 100; sort classes.txt -k 2 -n > classes.sorted.txt

# 求最近邻
./distance vectors.bin