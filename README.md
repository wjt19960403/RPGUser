用户体系构架：用户->英雄->装备（分武器与防具）->宝石

User（用户） ：{
    基础属性：
        userName（用户姓名） : string
        level（用户等级） : number
        currentExp（当前经验值） : number
        diamonds（钻石） : number
        gold（金币） : number

    高级属性：
        totalExp（当前等级的经验值上限） ：level*(level+5)*10
    }

Hero（英雄）：{
    基础属性：
        name（姓名） : string;
        level（等级） ： number
        currentExp（当前经验值） ： number
        growth (升级三维成长) : number

    高级属性：
        totalExp（当前等级的经验值上限） ：level * ( level + 5 ) * 10

        MaxHP（英雄最大生命值）： 480 + ( 20 + strength ) * 2.0

        MaxMP（英雄最大魔法值）： 360 + ( 20 + intelligence ) * 1.2

        attack（英雄攻击力）： 36 + aglity * 1.0

        defence（英雄防御力）： 8 + aglity * 0.3

        aglity（英雄敏捷）： 12 + level * growth

        strength(英雄力量): 15 + level * growth

        intelligence(英雄智力)：10 + level * growth

        powerValue（英雄战斗力）： 英雄基础战斗力:( aglity + strength + intelligence ) * 30 + ( MaxHP + MaxMP ) * 0.75 + attack * 2.5 + defence * 5
                                + 武器战斗力

}

Weapon（武器）：{
    基础属性：
        name（武器名称） : string;
        quality（品质）  ： number
        attack（武器攻击力） ： number
    
    高级属性：
        powerValue（武器战斗力） ： 武器基础战斗力:attack * 2.5 * ( quality + 12) / 10
                                + 宝石战斗力
}

Armor（防具）：{
    基础属性：
        name（防具名称） : string;
        quality（品质）  ： number
        defence（防具防御力） ： number

    高级属性：
        powerValue（防具战斗力） ： 防具基础战斗力：defence * 5 * ( quality + 12) / 10
                                + 宝石战斗力
}

Jewel（宝石）{
    基础属性：
        name（姓名） : string
        quality（品质）  ： number

    高级属性：
        powerValue（宝石战斗力） ： 15 * ( quality + 12) / 10
}