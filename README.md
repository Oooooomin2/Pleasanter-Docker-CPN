# Pleasanter-Docker-CPN
PleasanterをCentOS7+Nginxコンテナ上で起動します。  
DBコンテナにはPostgreSQLが入っています。

# 利用方法
1.以下のコマンドで当リポジトリをクローンします。  
2.docker-compose.ymlファイルと同じフォルダ内でコマンド"docker-compose up -d"を入力し、Enterを押します。  
3.完了後、"docker ps -a"コマンドでCentOS7のコンテナIdを控えます。  
4."docker exec -it {3で控えたコマンド} bash"と入力し、Enterを押します。この操作でCentOS7コンテナ内に入ります。  
5."cd web/pleasanter/Implem.CodeDefiner"と入力し、Enterを押します。  
6."dotnet Implem.CodeDefiner.NetCore.dll _rds"と入力し、Enterを押します。ドワーーーーっと出てきますが、最後のほうに<SUCCESS ～>みたいなのが出たら成功です。  
7."systemctl restart nginx"と入力し、Enterを押します。これでNginXが再起動されます。 
8.ホストに戻り、ブラウザを立ち上げ、"127.0.0.1:8080/users/login"と入力してEnterを押します。  
9.Pleasanterのログイン画面が出てきたら成功です！  

# その他
今回はあくまでDemo用です。PostgreSqlコンテナを削除したらデータも消えちゃいます。永続化を行いたい方はローカルにPostgreSqlを入れてコンテナからマウントさせてください。
