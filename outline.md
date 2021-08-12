# OUTLINE of how to study Docker(Ansible(Vagrant(SSH)))



|Step|項目|やること|ポイント|
|---|---|---|---|
|1|SSH|２台の物理PCを用意しSSHで接続する。|ログインユーザーの公開鍵・秘密鍵の生成、配置
|2|Vagrant|Vagrant と Virtualbox を使ってVMを導入・設定・破棄する。|Vagrant コマンド、Vagrantfileの書式・設定項目
|3|SSH+Vagrant|Vagrant で構築した2台のVM間でSSH接続する。|マルチマシン設定、Vagrantでどこまで設定するか
|4|Ansible|簡単なPlaybookをローカルで実行|Playbook(YAML)の書式、設定項目
|5|Ansible|簡単なPlaybookをリモートで実行|Playbook(YAML)の書式、設定項目
|6|Ansible|複雑なPlaybookをリモートで実行|Playbook(YAML)の書式、設定項目
  

●各Stepの目指すところ：
1. 物理的に２台のPCを用意し、１台からもう１台にSSHでログインできるようになる。
2. vagrantコマンドとVagrantfileで、VMを容易に導入・設定・破棄できるようになる。
3. Vagrantfileで２台のVMを設定し、１台の仮想マシンからもう１台の仮想マシンにSSHでログインできるようになる。どこまでをVagrantfileで設定し、どこからをプロビジョニング（Ansible）で設定するのかを見極める。
4. ローカルマシン自身に対して、Ansibleの簡単なPlaybookを実行させることができる。
5. ローカルマシンから操作して、リモートサーバーに対して、Ansibleの簡単なPlaybookを実行させることができる。
6. ローカルマシンから操作して、リモートサーバーに対して、AnsibleのPlaybookを書いて任意の設定ができるようになる。

## Step1.２台の物理PCを用意しSSHで接続する
1. 物理的に２台のPCを学習環境として用意する。
2. PC1(Ubuntu)をリモートサーバー、PC2(UbuntuとVMでWindows10)をローカルマシンとする。
3. PC1に「openssh-server」をインストール、リモートログイン用のユーザーを作成し、ssh-keygenして秘密鍵と公開鍵を用意する。
4. ローカルマシン

|ポイント|実例|備考|
|---|---|---|
|リモートSSHサーバーの公開鍵|Remote:/etc/ssh/ssh_host_ecdsa_key.pub|接続時にフィンガープリントでサーバーの真性確認|
|リモートSSHサーバーの秘密鍵|Remote:/etc/ssh/ssh_host_ecdsa_key||
|ログインユーザーの鍵ペア作成|||
|ログインユーザーの公開鍵の配置|Remote:~/.ssh/authorized_keys||
|ログインユーザーの秘密鍵の配置|Local:~/.ssh/authorized_keys||
|ローカルマシンにリモートサーバーを登録|~/.ssh/known_hosts||

## Step2.Vagrant と Virtualbox を使ってVMを構築・設定・破棄する
1. まずは `vagrant up` してみる。
2. boxを指定して仮想マシンを起動、停止、破棄してみる。
3. ホスト名やIPアドレスを指定してみる。
4. vagrantでどこまで設定するか・シェルプロビジョニング

## Step3.Vagrant で構築した2台のVM間でSSH接続する
1. Vagrantfileに２台のVMの設定を記述する。
2. SSHの設定をする。

## Step4.簡単なPlaybookをローカルで実行

## Step5.簡単なPlaybookをリモートで実行

## Step6.複雑なPlaybookをリモートで実行
