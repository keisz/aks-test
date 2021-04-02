# AKS on AzureStack HCI のデプロイテスト用マニフェスト  

AzureStack HCI上に構成したAKSにリソースをデプロイしてみるサンプル用コード  

## nginx-dev.yaml
nginxをtype:loadbalancerで公開しています。

## helloworld-lb.yaml
デプロイし、LoadBalancer IPにアクセスするとPod nameが表示されます。リロードすることでロードバランスされていることを確認できます。

## wordpress-deployment.yaml / mysql-deployment.yaml
WordpressとMysqlをデプロイして動作することを確認します。
*StorageClass: default* を使い、PV/PVCを作成して利用しています。
サービスはLoad Balancerで公開していますので、WebブラウザでLoadBalancer IPにアクセスすることでWordpressにアクセスできます。  


### コマンド  
- サービスの確認
  `kubectl get svc`

- ストレージクラスの確認  
  `kubectl get sc`  

- マニフェストの適用  
  `kubectl apply -f file.yaml`

- Podの確認  
  `kubectl get pod`






