# DISS-CF
This is for our ACM MM 2023 paper 3954
DISS-CF: Direct Item Session Similarity enhanced Collaborative Filtering for GCN-based Recommender Systems

Anyone who want to use this plugin to import GCN-based Recommender System can do as the following:
1. download the TWSF.py file and put it to your project directory
2. Call the method and pass the parameters and the method would return an (#users+#items, #users+#items) adjcency matrix
3. Using the new adjacency matrix in the following programming

How LightGCN applies DISS-CF method is also provided and the code of LightGCN is from https://github.com/kuandeng/LightGCN

## Environment
The code has been tested running under Python 3.6, tensorflow 2.5.0 on PyCharm 2021.3.3 (Professional Edition).

## Examples to run a 3-layer LightGCN with Gowalla dataset
* Command
```
python LightGCN.py --dataset gowalla --regs [1e-4] --embed_size 64 --layer_size [64,64,64] --lr 0.001 --batch_size 2048 --epoch 1000 --session_len 5
```
* Output log :
```
      ...
n_users=29858, n_items=40981
n_interactions=1027370
n_train=810128, n_test=217242, sparsity=0.00084
      ...
Epoch 1 [35.9s]: train==[0.47631=0.47616 + 0.00015]
Epoch 2 [30.9s]: train==[0.21221=0.21169 + 0.00053]
Epoch 3 [30.9s]: train==[0.15378=0.15304 + 0.00074]
Epoch 4 [30.9s]: train==[0.12704=0.12615 + 0.00089]
Epoch 5 [30.9s]: train==[0.11185=0.11084 + 0.00100]
Epoch 6 [31.0s]: train==[0.10044=0.09934 + 0.00110]
Epoch 7 [31.3s]: train==[0.09235=0.09117 + 0.00118]
Epoch 8 [31.2s]: train==[0.08714=0.08589 + 0.00125]
Epoch 9 [31.0s]: train==[0.08137=0.08006 + 0.00131]
Epoch 10 [30.9s]: train==[0.07731=0.07594 + 0.00137]
      ...
Epoch 1000: train==[0.01099=0.00454 + 0.00646 + 0.00000], recall=[0.48466], precision=[0.38556], ndcg=[0.50663]
Epoch 1000 [216.2s + 165.8s]: test==[0.12061=0.11420 + 0.00641 + 0.00000], recall=[0.18340], precision=[0.05650], ndcg=[0.15663]
Best Iter=[46]@[48626.2]	recall=[0.18442], precision=[0.05668], ndcg=[0.15682]
```
=======
