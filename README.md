# Roll20API
團體檢定載入 5E OGL 配置 (在安裝API之後進入遊戲需執行):

!group-check-config --import 5E-OGL

團體檢定巨集 (包含套用傷害，套用傷害的API已被拆出，需要手動載入JS [ApplyDamage.js]):

!group-check {{ --?{屬性豁免|力量,Strength Save|敏捷,Dexterity Save|體質,Constitution Save|智力,Intelligence Save|感知,Wisdom Save|魅力,Charisma Save} --process --subheader vs DC ?{DC} --button 套用傷害 !apply-damage ~dmg [[?{Damage}]] ~type ?{豁免後傷害|一半,half|無傷,none} ~DC ?{DC} ~saves RESULTS(,) ~ids IDS(,) }}
