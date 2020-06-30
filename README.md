# Roll20API DND 常用API
Ammo、5th Edition OGL by Roll20 Companion、GroupCheck、GroupInitiative、TokenMod、Aura/Tint HealthColors、ApplyDamage.js 、StatusInfo.js


-- 骰先攻
> !group-init

-- 清除先攻
> !group-init --clear

StatusInfo API Marco
StatusInfo 需要手動載入JS，不能用一鍵式安裝，裝完之後要重新RESET一次，之後重新設定一次狀態，設定為沒有英文的。 

-- 狀態設定 
> !token-mod ?{Status|專注, --set statusmarkers#!blue|準備, --set statusmarkers#!stopwatch|-, |目盲, --set statusmarkers#!bleeding-eye --flip light_hassight|魅惑, --set statusmarkers#!broken-heart|耳聾, --set statusmarkers#!edge-crack|恐懼, --set statusmarkers#!screaming|被擒, --set statusmarkers#!grab|隱形, --set statusmarkers#!ninja-mask|無力, --set statusmarkers#!interdiction|麻痺, --set statusmarkers#!pummeled|石化, --set statusmarkers#!frozen-orb|中毒, --set statusmarkers#!chemical-bolt|伏地, --set statusmarkers#!back-pain|束縛, --set statusmarkers#!fishing-net|震懾, --set statusmarkers#!fist|昏迷, --set statusmarkers#!sleepy|-, |死亡, --set statusmarkers#=dead|-, |清除狀態, --set statusmarkers#-bleeding-eye#-broken-heart#-edge-crack#-screaming#-grab#-pummeled#-aura#-chemical-bolt#-back-pain#-fishing-net#-fist#-frozen-orb#-interdiction#-sleepy#-ninja-mask#-dead|清除所有, --set statusmarkers#-bleeding-eye#-broken-heart#-edge-crack#-screaming#-grab#-pummeled#-aura#-chemical-bolt#-back-pain#-fishing-net#-fist#-frozen-orb#-interdiction#-sleepy#-ninja-mask#-angel-outfit#-overdrive#-blue#-stopwatch#-archery-target#-dead}


-- 清除狀態
> !token-mod --set statusmarkers#-bleeding-eye#-broken-heart#-edge-crack#-screaming#-grab#-pummeled#-aura#-chemical-bolt#-back-pain#-fishing-net#-fist#-frozen-orb#-interdiction#-sleepy#-ninja-mask#-angel-outfit#-overdrive#-blue#-stopwatch#-archery-target#-dead


-- 團體檢定 !group-check API Marco
> !group-check {{
--?{屬性豁免|力量,Strength Save|敏捷,Dexterity Save|體質,Constitution Save|智力,Intelligence Save|感知,Wisdom Save|魅力,Charisma Save}
--process
--subheader vs DC ?{DC}
--button 套用傷害 !apply-damage
~dmg [[?{Damage}]]
~type ?{豁免後傷害|一半,half|無傷,none}
~DC ?{DC}
~saves RESULTS(,)
~ids IDS(,)
}}
