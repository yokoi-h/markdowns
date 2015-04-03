# クライアントCLIコマンド体系

## globalサブコマンド
```
% gobgpcli global rib //global-ribの表示
```

## neighborサブコマンド
```
 % gobgpcli neighbor                                                                            //neighborの状態表示(一覧)
 % gobgpcli neighbor <neighbor address>                                                         //neighborの状態表示
 % gobgpcli neighbor <neighbor address> shutdown                                                //neighborのshutdown
 % gobgpcli neighbor <neighbor address> reset                                                   //neighborのreset
 % gobgpcli neighbor <neighbor address> -f <family> softreset                                   //neighborのsoftreset
 % gobgpcli neighbor <neighbor address> -f <family> softresetin                                 //neighborのsoftresetin
 % gobgpcli neighbor <neighbor address> -f <family> softresetout　                              //neighborのsoftreset
 % gobgpcli neighbor <neighbor address> enable                                                  //neighborのenable
 % gobgpcli neighbor <neighbor address> disable                                                 //neighborのdisable
 % gobgpcli neighbor <neighbor address> -f <family> local-rib                                   //neighborのlocal-rib表示
 % gobgpcli neighbor <neighbor address> -f <family> adj-rib-in                                  //neighborのadj-rib-in表示
 % gobgpcli neighbor <neighbor address> -f <family> rib adj-rib-out                             //neighborのadj-rib-out表示
 % gobgpcli neighbor <neighbor address> -f <family> applypolicy                                 //neighborのapplypolicy追加
 　add <import policy name> <export policy name> <default import policy> <default export policy>
 % gobgpcli neighbor <neighbor address> -f <family> applypolicy del　　　　　　　                 //neighborのapplypolicy削除
 % gobgpcli neighbor <neighbor address> -f <family> applypolicy                                 //neighborのapplypolicy表示
 ```

## policyサブコマンド
### prefix
```
 % gobgpcli policy prefix add <prefix name> <prefix> //prefix追加
 % gobgpcli policy prefix del                        //prefix全削除
 % gobgpcli policy prefix del <prefix name>          //prefix削除
 % gobgpcli policy prefix                            //prefix一覧表示
 % gobgpcli policy prefix <prefix name>              //prefix表示
```
### neighbor
```
 % gobgpcli policy neighbor add <neighbor name> <neighbor address> //neighbor追加
 % gobgpcli policy neighbor del                                    //neighbor全削除
 % gobgpcli policy neighbor del <neighbor name>                    //削除
 % gobgpcli policy neighbor                                        //neighbor一覧表示
 % gobgpcli policy neighbor <neighbor name>                        //表示
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