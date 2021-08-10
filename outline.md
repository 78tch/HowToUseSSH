# OUTLINE of how to study Docker(Ansible(Vagrant(SSH)))

1. 物理的に２台のPCを用意し、１台からもう１台にSSHでログインできるようになる。
2. Vagrant とVirtualbox を使って、Ubuntuマシン上に、複数台の仮想マシンを容易に導入・設定・破棄できるようになる。
3. １台の仮想マシンからもう１台の仮想マシンにSSHでログインできるようになる。
4. ローカルマシンから操作して、リモートサーバーに、AnsibleのPlaybookを実行させる。

## 物理的に２台のPCを用意し、１台からもう１台にSSHでログインできるようになる。
1. 物理的に２台のPCを学習環境として用意する。
2. PC1(Ubuntu)をリモートサーバー、PC2(UbuntuとVMでWindows10)をローカルマシンとする。
3. PC1に「openssh-server」をインストール、リモートログイン用のユーザーを作成し、ssh-keygenして秘密鍵と公開鍵を用意する。
4. ローカルマシン
