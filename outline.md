# OUTLINE of how to study Docker(Ansible(Vagrant(SSH)))



|Step|項目|やること|ポイント|
|---|---|---|---|
|1|SSH|２台のPCを用意しSSHで接続する。|公開鍵・秘密鍵の生成、配置
|2|Vagrant|Vagrant と Virtualbox を使って2台のVMを構築・設定・破棄する。|Vagrantfileの書式、設定項目
|3|SSH+Vagrant|Vagrant で構築した2台のVM間でSSH接続する。|少ない工程で実現
|4|Ansible|簡単なPlaybookをローカルで実行|Playbook(YAML)の書式、設定項目
|5|Ansible|簡単なPlaybookをリモートで実行|Playbook(YAML)の書式、設定項目
|6|Ansible|複雑なPlaybookをリモートで実行|Playbook(YAML)の書式、設定項目

●各Stepの目指すところ：
1. 物理的に２台のPCを用意し、１台からもう１台にSSHでログインできるようになる。
2. Vagrant とVirtualbox を使って、Ubuntuマシン上に、複数台の仮想マシンを容易に導入・設定・破棄できるように、Vagrantfileを書けるようになる。
3. １台の仮想マシンからもう１台の仮想マシンにSSHでログインできるようになる。
4. ローカルマシン自身に対して、AnsibleのPlaybookを実行させることができる。
5. ローカルマシンから操作して、リモートサーバーに対して、AnsibleのPlaybookを実行させることができる。
6. ローカルマシンから操作して、リモートサーバーに対して、任意の設定をするAnsibleのPlaybookを書けるようになる。

## 物理的に２台のPCを用意し、１台からもう１台にSSHでログインできるようになる。
1. 物理的に２台のPCを学習環境として用意する。
2. PC1(Ubuntu)をリモートサーバー、PC2(UbuntuとVMでWindows10)をローカルマシンとする。
3. PC1に「openssh-server」をインストール、リモートログイン用のユーザーを作成し、ssh-keygenして秘密鍵と公開鍵を用意する。
4. ローカルマシン
