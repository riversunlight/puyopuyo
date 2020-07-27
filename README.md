# ぷよぷよ
消す判定どうやるのか気になったので作ってみた(BFSで実装)

## 説明
同じ色の四角(ぷよ)を4つつなげて消します。  
消えたぷよの上にあるぷよは落下します。  
落下したぷよにより、新しく4つつながったぷよはきえます(俗にいう連鎖)  

## このリポジトリのぷよぷよのルール
180秒間で、より高スコアを目指します。  
連鎖すると、得点が高くなります  

## 消すアルゴリズム
やり方としてはDFSもあったが、これだとグローバル変数を用意しないといけないので、ローカル変数だけでよい幅優先探索(BFS)を採択  
2ぷよを落とすので、その落ちたぷよを中心に、BFSで探索し4つ以上つながったものがあれば消す  
落下したら、動いたぷよすべてに対してBFSで消せるか判定して連鎖させています
