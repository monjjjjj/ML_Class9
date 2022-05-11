# ML_Class9
## DRL: Basic
1. 在RL裡我們遇到的問題是，當我們給機器一個輸入的時候，我們不知道“最佳的”輸出是什麼！
2. 當今天你發現要搜集有標註的資料很困難且人類也不知道正確答案是什麼的時候，就是使用RL的時候！
### What's RL?
1. 一樣有3個steps！
2. 訓練的目標：maximize the total reward！
3. reward function在定義的時候不只看action，還要看observation！
4. 如好找出一組network的參數使得R越大越好？
5. Actor就像Generator，Environment跟Reward就像Discriminator -> 就像GAN一樣
   但在GAN裡，Discriminator也是一個network，可以用gradient descent來訓練，而Environment跟Reward就像一個黑盒子一樣
6. 為什麼負的total reward就等於loss? 因為想要讓R越大越好，所以加一個負號，R越大他會越小，就像loss一樣
### 拿來做optimization常用的演算法 -> policy gradient
1. 聽起來似乎跟supervised-learning沒有什麼不同？

## DRL:Policy Gradient
1. 搜集資料這一段是發生在for迴圈裡！-> 所以RL的訓練過程很花時間！

## DRL: Actor-Critic
1. Value function是想要未卜先知，想要在遊戲尚未結束的時候就先猜測能夠得到多少的the discounted cumulated reward
2. Value function的數值是跟觀察的對象有關係的！
3. Critic有兩種常用的訓練方法：MC(要玩完整場遊戲才能讀到訓練資料) ＆ TD(希望不用玩完整場遊戲才能得到訓練資料)
4. Critic怎麼被用在訓練Actor上面？
5. Reinforcement learning 訓練的好不好跟sample的好不好關係非常大！

## DRL: When Reward Is Sparse
1. 假設大部分的reward都是0，代表你根本無法得知該action是好還是壞！
2. 我們只能想辦法去提供額外的reward，來幫助agent去學習 -> reward shaping！

## DRL: Imitation Learning (連reward都沒有的時候怎麼辦？)
1. 在沒有reward的情況下，要如何訓練agent去跟環境互動呢？ -> imitation learning
2. Behavior cloning會發生的問題：

   機器無法學到人類不會經歷某些狀況的情況下如何處理問題！

   機器無法判斷哪些行為該模仿，哪些不該模仿！
   
   機器的能力可能是有限的，所以無法完全模仿其行為，只能部分模仿！

3. 讓機器自己定義Reward：藉由demonstration of expert跟environment去反推reward function！
4. GAN跟IRL有異曲同工之妙：Generator -> Actor, Discriminator -> Reward function
