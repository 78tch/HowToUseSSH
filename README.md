# HowToUseSSH  
## index
1. リモートサーバー（SSH Server）の用意
2. ローカルマシン（SSH Client）の用意
3. まずはパスワード認証でログイン
4. 公開鍵認証でログイン
5. リモートサーバーの設定ファイル
6. ローカルマシンの設定ファイル
7. さらに詳細な設定
8. known_hosts ファイルの更新

## 1. リモートサーバーの用意
SSHサーバーには「openssh-server」を使います。
```Bash
user00@RMTSSHSRV:~$ sudo apt-get install openssh-server
```
この際に、「ホスト鍵」が生成され、フィンガープリントが表示されます。  
「ホスト鍵」を後で確認する方法としては、SSHサーバー自身でログインすれば、表示される。  
```Bash
user00@RMTSSHSRV:~$ ssh 127.0.0.1
```
また、` ssh-keygen -l ` をSSHサーバー自身で実行しても確認できる。  
```Bash
user00@RMTSSHSRV:~$ sudo ssh-keygen -l
: /etc/ssh/ssh_host_ecdsa_key
```


(ノートパソコンの蓋（液晶モニタ）を閉じてもサスペンドしない設定)  
``` bash
vi /etc/systemd/logind.conf
```
` HandleLidSwitch=ignore `  

## 2. ローカルマシンの用意
ログインするユーザーの「秘密鍵：id_rsa」と「公開鍵：id_rsa.pub」を作成する。  
「公開鍵」を、SSHサーバーの「 ~/.ssh/ 」に、「authorized_keys」とリネイムして置く。  
## 3. まずはパスワード認証でログイン
SSHサーバーで「パスワード認証」を有効にする。（学習のため。のちに無効にする。）
/etc/ssh/sshd_config 
PasswordAuthentication yes 
```Bash
user00@RMTSSHSRV:~$ sudo service ssh restart
```
とする。  

## 4. 公開鍵認証でログイン
## 5. リモートサーバーの設定ファイル
ホスト認証  
/etc/ssh/
* ssh_host_dsa_key
* ssh_host_dsa_key.pub
* ssh_host_ecdsa_key
* ssh_host_ecdsa_key.pub
* ssh_host_rsa_key
* ssh_host_rsa_key.pub


## 6. ローカルマシンの設定ファイル
## 7. さらに詳細な設定