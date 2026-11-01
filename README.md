## 簡化 nightbot 新增、刪除、修改指令

```
!addcom a -cd=5 -ul=moderator -a=!addcom $(query)
```

```
!addcom d -cd=5 -ul=moderator -a=!delcom $(query)
```

```
!addcom e -cd=5 -ul=moderator -a=!editcom $(query)
```

## w 變更隊友

```
!addcom !隊友 隊友名稱
```

```
!addcom w -cd=5 -ul=moderator -a=!editcom !隊友 $(query)
```

```
w 隊友名稱
```

## !+ - Session RP (tas.gg)

```
路徑: ACCOUNT COMMANDS > GAME ACCOUNT RELATED COMMANDS > [選擇你要的遊戲帳號] > SESSION RELATED > SESSION RP
```

```
Url example: https://cmds.tas.gg/example_url/example_url/rp
```

```
!addcom !+ $(eval const s=`$(urlfetch paste_your_url_here)`,b=s.split(" | [Updated")[0].replace(/^= RP Stats = \| Current Amount: /,"Current: ");s.includes("No RP")?b.replace(/ No RP has been gained or lost this session.*$/," 0 RP"):s.includes("lost")?b.replace(" || "," || -").replace(/ has been lost this session.*$/,""):s.includes("gained")?b.replace(" || "," || +").replace(/ has been gained this session.*$/,""):b)
```

## !底分 - Predator Cap Line (BR) (tas.gg)

```
路徑: ACCOUNT COMMANDS > GENERAL COMMANDS > RANKED RELATED > Predator Cap Line (BR)
```

```
Url example: https://cmds.tas.gg/example_url/br-predator?pc
```

```
!addcom !底分 $(eval "$(urlfetch paste_your_url_here)".replace(/.*\| (PC: [\d,]+ RP) \|.*/, "$1"))
```

## !top5 - Top 5 Ranked Players (BR) (tas.gg)

```
路徑: ACCOUNT COMMANDS > GENERAL COMMANDS > RANKED RELATED > TOP 5 RANKED PLAYERS (BR)
```

```
!addcom !top5 $(eval `$(urlfetch https://twitchapexstats.com/cmds/br-top-5?channel=nightbot&platform=pc&lang=en)`.replace(/.*(\#1.*) \|.*/, "$1").replace(/ - /g," "))
```

## !賽季剩餘 - Time Remaining In Ranked Split (tas.gg)

```
路徑: ACCOUNT COMMANDS > GENERAL COMMANDS > RANKED RELATED > TIME REMAINING IN RANKED SPLIT
```

```
Url example: https://cmds.tas.gg/example_url/timeleft
```

```
!addcom !賽季剩餘 $(eval const r = `$(urlfetch paste_your_url_here)`.match(/currently (.*?) remaining/); r ? "賽季剩餘: " + r[1].replace(/wks?/g, '週').replace(/ds?/g, '天').replace(/hrs?/g, '小時').replace(/mins?/g, '分鐘').replace(/,/g, '') : "無法取得時間")
```
