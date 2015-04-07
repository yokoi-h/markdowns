# クライアントCLIコマンド体系

## 基本パターン
gobgpcli \<subcommand> \<object>  opts...

## globalサブコマンド
### global-ribの表示
```shell
% gobgpcli global rib
```

## neighborサブコマンド
### neighborの状態表示
```shell
 % gobgpcli neighbor                                                                            //neighborの状態表示(一覧)
 % gobgpcli neighbor <neighbor address>                                                         //neighborの状態表示
```

### neighborの各種操作(shutdown/reset/softreset/enable/disable)
```shell
 % gobgpcli neighbor <neighbor address> shutdown                                               
 % gobgpcli neighbor <neighbor address> reset                                                  
 % gobgpcli neighbor <neighbor address> softreset -f <family>
 % gobgpcli neighbor <neighbor address> softresetin -f <family>
 % gobgpcli neighbor <neighbor address> softresetout -f <family>
 % gobgpcli neighbor <neighbor address> enable                                               
 % gobgpcli neighbor <neighbor address> disable                                              
```

### ribの表示(local-rib/adj-rib-in/adj-rib-out)
```shell
 % gobgpcli neighbor <neighbor address> local-rib -f <family>
 % gobgpcli neighbor <neighbor address> adj-rib-in -f <family>
 % gobgpcli neighbor <neighbor address> adj-rib-out -f <family> 
 
```

### policyの操作(add/delete/show)
```shell
# add
% gobgpcli neighbor <neighbor address> policy apply import -f <family> <import policy name> <default import policy>
% gobgpcli neighbor <neighbor address> policy apply export -f <family> <export policy name> <default export policy>
# del
% gobgpcli neighbor <neighbor address> policy delete import -f <family>
% gobgpcli neighbor <neighbor address> policy delete export -f <family>
# show
% gobgpcli neighbor <neighbor address> policy -f <family>
```

## policyサブコマンド(PrefixSet/NeighborSet/RoutingPolicy操作用のサブコマンド)
### prefix setの操作(add/delete/show)
```shell
# add
 % gobgpcli policy prefix add <prefix name> <prefix>
# del  prefix全削除
 % gobgpcli policy prefix del
# del  prefix名前指定削除
 % gobgpcli policy prefix del <prefix name>
# show  prefix一覧
 % gobgpcli policy prefix
# show  prefix名前指定表示
 % gobgpcli policy prefix <prefix name>
```
### neighbor setの操作(add/delete/show)
```shell
# add
% gobgpcli policy neighbor add <neighbor-set name> <neighbor address>
# del  NeighborSet全削除
% gobgpcli policy neighbor del      
# del  NeighborSet名前指定削除
% gobgpcli policy neighbor del <neighbor-set name>  
# show  NeighborSet一覧
% gobgpcli policy neighbor                                        
# show  NeighborSet名前指定表示
% gobgpcli policy neighbor <neighbor-set name> 
```
### routepolicy
```
 % gobgpcli policy routepoilcy add <policy name> condition <condtion> action <aciton> //routepolicy追加
 % gobgpcli policy routepoilcy del                                                    //routepolicy全削除
 % gobgpcli policy routepoilcy del <policy name>                                      //routepolicy削除
 % gobgpcli policy routepoilcy                                                        //routepolicy一覧表示
 % gobgpcli policy routepoilcy <policy name>                                          //routepolicy表示
 % gobgpcli policy routepoilcy brief                                                  //routepolicy一覧表示(簡易表示）
 % gobgpcli policy routepoilcy brief　<policy name>                                   //routepolicy表示(簡易表示）
```
